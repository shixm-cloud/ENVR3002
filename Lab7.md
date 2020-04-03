## Cloud Physics I
{% include mathjax.html %} 

**The 3rd problem is a homework assignment. Please submit your code and an one-page explanation for the figure you get and the question asked in Problem 3.**

### Problem 1. Saturation Vapor Pressure

As we mentioned in class, saturation vapor pressure _e<sub>s</sub>_ is a function of temperature only. You can calculate its value with the Bolton's equation,
\\[
e_s = 6.112 \exp\left( \frac{17.67 T}{T+243.5}\right)
\\]
where _T_ is temperature in degrees Celsius, and _e<sub>s</sub>_ is in hPa.

Now, please calculate the saturation pressure for the tmperatures given below by `T` and make plot of _e<sub>s</sub>_ with Matlab/Octave function `plot`.
```
T = (-30:1:30)';   % temperature values
```

After obtaining _e<sub>s</sub>_ in Matlab/Octave, please use the array of _e<sub>s</sub>_ and _T_ to calculate fractional change in _e<sub>s</sub>_ for each 1 degree increase in temperature, that is, calculating 
\\[
S = \frac{1}{e_s}\frac{d e_s}{d T} \times 100\%
\\]
You can call this _S_ as the sensitivity of _e<sub>s</sub>_ to temperature. Plot _S_ as a function of _T_ with the command `plot`.

_Can you say something about the response of atmospheric moisture to global warming based on the second figure you get?_


### Problem 2. Diurnal Cycle of Relative Humidity

The following is the temperature throughout one day, please _calculate the relative humidity (RH)_ for the entire day and plot RH as a function of time. Assume mixing ratio is 9 g/kg for all 24 hours and surface pressure is 1000 hPa.

```
time = (0:24)';   % hours
T = [14.41, 13.85, 13.33, 12.88, 12.51, 12.23, 12.00, 12.23, 12.88, 13.85, ...
     15.00, 16.15, 17.12, 17.77, 17.94, 18.00, 17.94, 17.77, 17.49, 17.12, ...
     16.67, 16.15, 15.59, 15.00, 14.41];
f3 = figure;
plot(time, T)
xlabel('time (h)')
ylabel('temperature ({\circ}C)')

% assume mixing ratio is 9 g/kg and surface pressure is 1000hPa for the 
% entire day (0 -- 24h), please calculate RH for the entire day.


```


