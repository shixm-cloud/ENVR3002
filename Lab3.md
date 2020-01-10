## 3. Thermodynamics I

In the exercises today you will explore the vetical structure of the atmosphere above Hong Kong. A set of observation data are given below. The first three problems are in-class exercises and the **last one** is a **homework assignment**, for which you should submit your script on Canvas.

### Problem 1: Temperature Profile and Tropopause

Firstly, copy the following lines to your script file to set up the vectors of observation data.
```
T = [300.54, 299.48, 298.53, 297.60, 296.75, 294.98, 293.22, 291.96, 291.52, ...
     291.25, 290.21, 286.64, 282.13, 277.68, 273.29, 269.22, 265.63, 259.86, ... 
     252.30, 243.56, 234.33, 229.56, 223.46, 216.49, 208.76, 200.06, 194.05, ... 
     203.41, 211.83, 216.56];
p = [100000.00, 97500.00, 95000.00, 92500.00, 90000.00, 87500.00, 85000.00, ...
     82500.00, 80000.00, 77500.00, 75000.00, 70000.00, 65000.00, 60000.00,  ...
     55000.00, 50000.00, 45000.00, 40000.00, 35000.00, 30000.00, 25000.00,  ... 
     22500.00, 20000.00, 17500.00, 15000.00, 12500.00, 10000.00,  7000.00,  ...
     5000.00,  3000.00];
z = [    49.58,   273.79,   503.63,   738.49,   978.93,  1224.79,  1475.96, ...
       1732.99,  1996.93,  2268.63,  2548.50,  3132.77,  3751.59,  4408.88, ...
       5111.48,  5868.45,  6693.25,  7599.61,  8600.50,  9718.53, 10993.89, ... 
      11708.78, 12489.58, 13349.18, 14308.12, 15398.06, 16679.47, 18732.73, ...
      20771.87, 23965.36];
```
These are data obtained at 00:00, September 15, 2018. You can display the data nicely by putting them in a MATLAB _table_. The following code does this job.
```
data = table(z', p', T', 'VariableNames', ["z", "p", "T"]);
disp(data)
```

Now, please make a plot of temperature profile using _T_ and _z_, and identify the **height of tropopause** and the **temperature at the tropopause**. _T_ and _z_ given above are in the units of K and meter, respectively, please convert them to degree Celsius and kilometer in your plot. \[hint: you need to use the command `plot` for this task\].

Can you also find out the pressure at the tropopause?

### Problem 2: Density Profile
{* include mathjax.html *}
Recall that the ideal gas law is
\\[
p = \rho R T
\\]
where \\( R = 287\,J K^{-1} kg^{-1}\\)
