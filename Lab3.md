## 3. Thermodynamics I

In the exercises today you will explore the vetical structure of the atmosphere above Hong Kong. A set of observation data are given below. The first three problems are in-class practice and the **last one** is a **homework assignment**, for which you should submit your script on Canvas.

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
{% include mathjax.html %}

Recall that the ideal gas law is
\\[
p = \rho R T
\\]
where \\( R = 287\,\mathrm{J\,K^{-1} kg^{-1}}\\). Please use the ideal gas law and data given above to calculate the **vertical profile of density**. You should save a to a vector named `rho`. Plot density as a function of height. Can you identify the density at the tropopause? What fraction is it of the density at surface (1000hPa)?

Now, if we assume the density profile is exponential with height, can you figure out the value of the **scale height** using the fraction of the density at tropopause to that at surface? Save you calculation result to `H`.

Please plot the observed density profile and exponential profile in the same plot to verify if the exponential profile is a good approximation. The syntax to plot two lines in the same figure is
```
plot(x1, y1, s1, x2, y2, s2)
```
where `s1` and `s2` are character strings to specify line properties. For example, you can set `s1` to `'r'` and `s2` to `'b'` for using red and blue colors in your plot.

### Problem 3 Hydrostatic Balance

As we learned in class, the hydrostatic balance equation is 
\\[
\frac{\partial p}{\partial z} = -g\rho
\\]
If we approximate the equation above with finite difference, we have
\\[
\frac{\Delta p}{\Delta z} = -g\rho
\\]
where \\(\Delta p\\) and \\(\Delta z\\) are the change _p_ and _z_ from level _k_ to level _k_+1. \\(g=9.8\,\mathrm{m\,s^{-2}}\\) is the gravitational constant.

Now, please calculate \\(\Delta p\\) and \\(\Delta z\\) with the observation data you have. You can save the results in two vectors `dpObs` and `dzObs`, each of which should have 29 elements. 

Next, calculate the average density for 29 layers. For each layer, you can use the average of density at the bottom and the top of that layer, i.e. `(rho(k) + rho(k+1)) / 2`. Save the resulting vector to `rhoAvg`.

Lastly, use `dzObs` and `rhoAvg` to calculate the pressure changes required by the hydrostatic balance equation. Save your result to `dpHyd`. Display `dpHyd` and `dpObs` side by side like the following to check how good is the hydrostatic balance approximation for a real atmosphere.
```
kLayer     dpHyd     dpObs
______    _______    _____

   1        -2520    -2500
   2      -2526.3    -2500
   3      -2522.4    -2500
 ...          ...      ...
  29      -2042.3    -2000
  
```

### Problem 4<sup>*</sup> Hypsometric Equation 
  <sup>*</sup> _This is a homework assginment and you need to submit your code on Canvas_

With the exercises above, you have learned on how to convert between layer thickness in pressure and in height. The hypsometric equation relates an atmospheric pressure ratio to the thickness of an atmospheric layer. 

\\[
z_{k+1} - z_k = \frac{R T_{k+\frac12} }{g} \ln\left(\frac{p_k}{p_{k+1}}\right)
\\]
where \\(T_{k+\frac12}\\) is the mean temperature of the atmosphere layer between height \\(z_{k}\\) and \\(z_{k+1}\\) (\\(p_{k+1}\\) and \\(p_k\\)), 
\\[
T_{k+\frac{1}{2}} = \frac(T_k + T_{k+1}}{2}
\\]

Because the hypsometric equation uses temperature directly, instead of calculating density as an intermediate step, it is more convinient.



