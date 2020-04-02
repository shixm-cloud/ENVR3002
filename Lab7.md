## Cloud Physics I
{% include mathjax.html %} 

**The 3rd problem is a homework assignment. Please submit your code and an one-page explanation for the figure you get and the question asked in Problem 3.**

### Problem 1 Saturation Vapor Pressure

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

