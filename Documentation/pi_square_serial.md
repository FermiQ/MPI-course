# Documentation for `pi_square_serial.py`

## Overview

This script calculates an approximation of Pi squared (π²) using a serial (non-parallel) method. It computes the sum of the series 1/(n²) for n from 1 to a specified limit (`finval`). The sum of this infinite series is known to be π²/6. Therefore, by calculating this sum and multiplying by 6, we get an approximation of π². This script is intended to be a serial counterpart to parallel versions, likely used for comparison or as a starting point in learning parallel programming.

## Key Components

The script consists of a single block of executable code:

*   **Initialization**:
    *   `finval = 10000000`: Sets the number of terms to sum in the series.
    *   `pi_square = 0.0`: Initializes the variable to store the sum of the series.
*   **Summation Loop**:
    *   `for i in range(finval):`: Iterates from `0` to `finval-1`.
    *   `pi_square += 1.0 / (float(i+1)**2)`: Adds the next term (1/((i+1)²)) to `pi_square`. `i+1` is used because the series starts from n=1.
*   **Result Calculation and Output**:
    *   `print("Pi^2 = {:.10f}".format(pi_square*6.0))`: Multiplies the sum by 6 to get π² and prints the result formatted to 10 decimal places.

## Important Variables/Constants

*   `finval`: An integer representing the upper limit of the summation (number of terms). A larger `finval` generally leads to a more accurate approximation of π² but takes longer to compute.
*   `pi_square`: A float variable that accumulates the sum of the series 1/(n²).

## Usage Examples

To run this script, simply execute it with a Python interpreter:

```bash
python pi_square_serial.py
```

Expected output (will be a single line):

```
Pi^2 = 6.1644854083
```
(The exact value will depend on `finval`)

## Dependencies and Interactions

*   **Dependencies**:
    *   This script has no external library dependencies beyond standard Python.
*   **Interactions**:
    *   This is a purely serial script; there are no interactions with other processes or systems. It runs entirely on a single CPU core.
```
