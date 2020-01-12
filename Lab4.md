
## 4. Thermodynamics II

### Problem 1 Specific Heats

Suppose the volume of our class room is 300 m<sup>3</sup>. For initial temperatures `T0` given be the following vector, how much heat is needed to be removed to cool the room to 21 <sup>o</sup>C?
```
T0 = 24:33
```
Assume the pressure in the room is always the same as the pressure outside, which is constant `p = 1000` hPa. You can ignore the change in the mass of air in the room during cooling, but should be aware of the difference in initial mass (due to the difference in temperature). The specific heats at constant pressure and constant volume are 1004 and 717 J kg<sup>-1</sup> K<sup>-1</sup>, respectively. For your reference, 1 kWh = 3.6 <span>&#215;</span> 10<sup>6</sup> J.

### Problem 2 Moist adiabatic process

In class, we learned that the dry adiabatic lapse rate is 9.8 K/km. For moist adiabatic process, the lapse rate is lower because of the latent heat release during the phase change of water. In this exercise you will compute the lapse rate in moist adiabatic lifting. 

During moist adiabatic lifting, the air is always saturated. For given temperature and pressure, you can calculate saturation mixing ratio with the code below. Mixing ratio is defined as the ratio of the mass of water vapor to that of dry air. So 0.010 kg/kg means there is 0.01 kg water vapor in per kilogram of dry air.
```
% saturation vapor pressure in Pa
es = 611.2 * exp(17.67 * (T-273.15) ./ (T - 29.65));
% saturation mixing ratio in kg/kg
rs = (287.0/461.5) * es ./ (p - es);
```
{% include mathjax.html %}

The moist diabatic lapse rate is defined by the following expression,
\\[
\Gamma_m = \frac{g}{c_{pd}} \frac{1+r_s}{1 + r_s c_{pv} /c_{pd}}  \frac{1 +
L r_s/(R_d T)}{1 + L^2 r_s (1+r_s/\epsilon)/[R_v T^2 (c_{pd} + r_s c_{pv})]}
\\]
where \\(g = 9.8\,\mathrm{m\,s^{-2}}\\) is the gravitational constant, \\(c_{pd} = 
1004\,\mathrm{J\,kg^{-1}\,K^{-1}}\\) and \\(c_{pv} = 1870\,\mathrm{J\,kg^{-1}\,K^{-1}}\\) are specific heat of dry air and water vapor, respectively, at constant pressure. \\(L = 2.5\times 10^6\,\mathrm{J\,kg^{-1}}\\) is the latent heat of vaporization. 
\\(R_d = 287\,\mathrm{J\,kg^{-1}\,K^{-1}}\\) and \\(R_v = 461\,\mathrm{J\,kg^{-1}\,K^{-1}}\\) are gas constants of dry air and water vapor, respectively. \\( \epsilon = R_d/R_v\\).

Please write a script to calculate the moist adiabatic lapse rate for the temperature and pressure profiles given below. Display the results along with temperature and pressure in a table.
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
```




