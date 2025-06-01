# Documentation for `hello_mpi.py`

## Overview

This script is a basic "Hello, World!" program for MPI (Message Passing Interface) using the `mpi4py` library in Python. Its purpose is to demonstrate the fundamental MPI concepts of communicator, process rank, and communicator size. It initializes MPI, determines the rank of the current process and the total number of processes, and then prints this information to the console. This is often the first program one runs to verify that an MPI environment is correctly set up.

## Key Components

The script consists of a single block of executable code with no functions or classes defined. The key operations are:

*   **MPI Initialization**: Implicitly done by importing `MPI` from `mpi4py` and accessing `MPI.COMM_WORLD`.
*   **Communicator Access**: `my_comm = MPI.COMM_WORLD` gets the default global communicator, which includes all MPI processes launched.
*   **Getting Communicator Size**: `size = my_comm.Get_size()` retrieves the total number of MPI processes in the `COMM_WORLD` communicator.
*   **Getting Process Rank**: `rank = my_comm.Get_rank()` retrieves the unique ID (rank) of the current MPI process within the `COMM_WORLD` communicator. Ranks range from `0` to `size-1`.
*   **Printing Information**: `print ('I am rank:', rank, ' out of:', size)` outputs the rank of the current process and the total number of processes.

## Important Variables/Constants

*   `my_comm`: An MPI communicator object (`MPI.Comm`). It represents the group of processes involved in the communication (here, `MPI.COMM_WORLD`, which includes all processes).
*   `size`: An integer storing the total number of processes in the `my_comm` communicator.
*   `rank`: An integer storing the unique identifier (rank) of the current process within the `my_comm` communicator.

## Usage Examples

To run this script, you typically use an MPI launcher like `mpiexec` or `mpirun`. The `-n` flag specifies the number of processes to launch.

```bash
mpiexec -n 4 python hello_mpi.py
```

Expected output (the order of lines may vary):

```
I am rank: 0  out of: 4
I am rank: 1  out of: 4
I am rank: 2  out of: 4
I am rank: 3  out of: 4
```

## Dependencies and Interactions

*   **Dependencies**:
    *   `mpi4py`: This script requires the `mpi4py` Python library, which provides Python bindings for MPI.
    *   An underlying MPI implementation (e.g., Open MPI, MPICH) must be installed on the system.
*   **Interactions**:
    *   Each process runs the same script independently.
    *   There is no direct communication (sending or receiving messages) between the MPI processes in this particular script beyond the initial setup and coordination by the MPI runtime. Each process independently queries MPI for its rank and the size of the communicator.

```
