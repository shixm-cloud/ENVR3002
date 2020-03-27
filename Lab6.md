## Radiation II
{% include mathjax.html %}
**The 2nd problem is a homework assignment. Please submit your code and an one-page explanation (PDF format is preferred) of the calculation you did.**

### Problem 1. Optical Depth

In class, we explained that the absorption of radiation by a layer of gas is determined by the following equation,

\\[
I_{\lambda} = I_{\lambda 0} e^{-\tau_{\lambda}\sec\theta} = I_{\lambda 0} T_{\lambda}
\\]
where \\(I_{\lambda 0}\\) is the incident radiation intensity,
\\[
\tau_{\lambda} = \int_z^{z_0} k_{\lambda}\rho r\, dz
\\]
is the _normal optical depth_, and 
\\[
T_{\lambda} = e^{-\tau_{\lambda}\sec\theta} 
\\]
is transmissivity. 

Now suppose parallel beam radiation is passing through a layer which is 100 m thick with air density \\(\rho=1\,\mathrm{kg\,m^{-3}}\\), and contains an absorbing gas with an average mixing ratio \\(r=0.1\,\mathrm{kg\,kg^{-1}}\\). The beam is directed at an angle of 60<sup>o</sup> relative to the normal to the layer. Please calculate the normal optical depth, transmissivity, and absorptivity of the layer at wavelengths \\(\lambda_1\\), \\(\lambda_2\\), \\(\lambda_3\\), for which the mass absorption coefficients are 10<sup>-3</sup>, 10<sup>-1</sup> and 1 m<sup>2</sup>kg<sup>-1</sup>.

```matlab
% absorption coefficients
k = [1.0e-3, 0.1, 1]';
% normal optical depth
tau = ?;
% transmissivity
T = ?;
% absorptivity
a = ?;

% display the result
disp('      lambda1  lambda2  lambda3')
fprintf('tau  %7.3f  %7.3f  %7.3f\n', tau)
fprintf('T    %7.3f  %7.3f  %7.3f\n', T)
fprintf('a    %7.3f  %7.3f  %7.3f\n', a)
```

### Problem 2. Monochromatic Flux Density and Reflectivity

A body is emitting radiation with the following idealized spectrum of monochromatic flux density.
\\[
F_{\lambda} = \begin{cases}
0 \\
1.0 \\
0.5 \\
0.2 \\
0
\end{cases}
\\]


