# Determination of Dv(x) values of cumulative particle size distribution (PSD)
## Description
Program is designed for determination of the cumulative distribution parameters Dv(x), which can be used to describe the cumulative particle size distribution. For example, if the Dv(90) = 844 um, this means that 90% of the sample has a size of 844 um or smaller. Dv(50) value is showing the median diameter of the distribution. Arbitrary Dv(x) value in range from 0.0 to 100.0 can be calculated using the approach described below. Inside a channel the linear interpolation can be applied to calculate arbitrary D_0:

<p align="center">
<img src="/Images/Figure_1.png" alt="Figure 1" width=70%>
</p>

When X_L, X_H, D_L and D_H are determined, it is possible to calculate:

<p align="center">
<img src="/Images/Equation_1.png" alt="Equation 1" width=30%>
</p>

## Usage of the program
In a program folder it is possible to find two text files – `Input_data.txt` and `Output_data.txt`. The structure of the first file should be the following: 1st line is a path to the Excel file with PSD data for the desired material (absolute or relative path). The way, how PSD data is organized in Excel file is standardized. Next lines in the input file form a list of desired x values for which Dv(x) values should be calculated. After the necessary calculations the output file will contain the set of Dv(x) values. During the program execution some additional information are shown in the console.

To run the program the following command should be executed:
```
$ python Program.py
```
## Testing
Performance of the program was tested on a set of PSD data of different mineral materials. To be sure that designed program shows correct results, it’s some output Dv(x) values (for x equal to 10, 50 and 90) were compared with the output from software of Malvern Mastersizer 3000 laser diffraction particle size analyzer. The results of comparison can be found in the following table.

<p align="center">
<img src="/Images/Table_1.png" alt="Table 1" width=90%>
</p>

## Conclusions
Analyzing the data from the table above, the values for Dv(x) calculated using the created program and using the Mastersizer 3000 software completely coincide. This means that the Mastersizer's program uses the same linear interpolation algorithm as our developed program. Therefore, we can conclude that the developed program can be successfully used to determine the values of Dv(x) for any possible values of x in the domain 0.0 ≤ x ≤ 100.0.

## Licence
Circles packaging simulation code in this project is available under the `GPLv3` license. You can find the license file here: [LICENSE](/LICENSE)