# Crush Coefficient Calculator
Converts an uploaded image to an OBJ Mesh surface. 

## Homepage and file access
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/opeyemiman/CrushCoefficientCalculator/main)



## Main Notebook
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/opeyemiman/CrushCoefficientCalculator/main?urlpath=voila%2Frender%2FCrushCoefficientCalculator.ipynb)



# Quick start

On Coefficients, choose whether you know b0 and b1 or A and B.
Enter width, mass, and the selected coefficient pair.
Choose Manual list, Range, or Linspace for each field, then calculate.
Use Statistics or Export after results appear.
What each calculation does
From b0 and b1: A = (m/w0)b0b1, B = (m/w0)b1^2, and G = A^2/B.

From A and B: b1 = sqrt(Bw0/m), b0 = A(w0/m)/b1, and G = A^2/B.

w0 is crush-zone width and m is mass. Width and mass must be positive. B must be positive for the inverse calculation.

Deriving b0 and b1
The Derive tab fits V = b0 + b1C through (C1,V1) and (C2,V2). It uses b1=(V2-V1)/(C2-C1) and b0=V1-b1C1. C1 and C2 cannot be equal.

Entering multiple values
Manual list: 5, or 5, 6, 7, or [5, 6, 7].
Range: start, stop, step. Stop is included when it lies on the sequence.
Linspace: start, stop, and an exact count of evenly spaced points.
Every combination is evaluated. Two widths and three b1 values produce six rows when other inputs have one value.
For Excel, use =TEXTJOIN(",",TRUE,A1:A5) and paste the result into a Manual list field.
Units and assumptions
Use internally consistent units. Menus label values but do not convert length or speed. To preserve the original notebook behavior, mass entered as lbs is divided by 32.174 and used as slugs. Confirm that this matches your engineering convention.

This notebook performs arithmetic, not crash-reconstruction validation. Verify calibration sources, conventions, inputs, and applicable professional methods before relying on results.

Velocity plot
The Velocity Plot tab draws V = b0 + b1x for every row in the selected result set. Choose the crush and velocity units that match the b0 and b1 data. The x-axis, y-axis, and each legend entry include units. The plot does not convert units, so b0 must use the selected velocity unit and b1 must use velocity-unit/crush-unit.

Statistics and exports
Statistics include count, mean, median, sample standard deviation, variance, range, percentiles, and an optional Student-t 95% confidence interval for the mean. Treat n below 10 cautiously. Exports include a combined CSV, histogram PNG plus bin CSV, and a printed comma-separated list.
