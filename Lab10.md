## Atmospheric Dynamics II

**Problem 2 is a homework assignment**. 

Data for today's exercises and homework can be downloaded from Canvas or 
[Sharepoint](https://gohkust-my.sharepoint.com/:u:/g/personal/shixm_ust_hk/Eb19PmycxeBBmb2-Y7BliBQBU4ZGShKXbWf7TnF9RRe3XA?e=GpHMaq).

### Problem 1. Geostrophic Wind and Gradient Wind

In this exercise, please complete the code to calculate geostrophic wind (u and v components), and use the code given to display it along with observed wind vectors. 
* _At which latitudes the geostrohic balance is a good approximation?_
* _Is the wind around low center and trough subgeostrophic or supergeostrophic?_

```matlab
load Lab10Data.mat
% plot contours of geopotential height
f1 = figure;
[LON, LAT] = meshgrid(lon, lat);
[C, h] = contour(LON(2:end-1, 2:end-1), LAT(2:end-1, 2:end-1), Z500(2:end-1, 2:end-1), (4900:100:5900), 'LineColor', 'k');
clabel(C, h, 'FontSize', 14, 'LabelSpacing', 300)
grid on
xlabel('longitude')
ylabel('latitude')
set(gca, 'FontSize', 14)
hold on
quiver(LON(2:4:end,2:4:end), LAT(2:4:end,2:4:end), u500(2:4:end,2:4:end), v500(2:4:end, 2:4:end), ...
    'Color', 'black', 'LineWidth', 1);
grid on
title('500 hPa Geopotential Height (Conoturs, m), Observed Wind (Black Arrows), and Geostrophic Wind (Red Arrows)')

% calculate geostrophic wind
dX = ?;   % [Hint: this should be a function of latitude]
dY = 6.37e6 * (1* pi/180);
% please calcualate the gradient of geopotential height in x and y directions
% [Hint: here you need to use finite difference to approximate the gradients]
Zx = ?; 
Zy = ?;
% f here is the Coriolis parameter
f = ?;
% ug and vg are the u and v components of the geostrophic wind
ug = ?;
vg = ?;

quiver(LON(2:4:end-1,2:4:end-1), LAT(2:4:end-1,2:4:end-1), ug(1:4:end,1:4:end), vg(1:4:end, 1:4:end), ...
    'Color', 'red', 'LineWidth', 1);
pbaspect([lon(end-1)-lon(2)  lat(end-1)-lat(2) 1])
hold off
```

### Problem 2. Distribution of Total Vorticity<sup>*</sup>

<sup>*</sup> **This is a homework assignment. Please submit your CODE on Canvas.**

{% include mathjax.html %} 

Total vorticity is the sum of relative vorticity and planetary vorticity, i.e. \\(\zeta+f \\). Please complete the code below (replace the question marks with your code) to calculate total vorticity and display it along with height contours.

[Hint: you need to some variables defined in Problem 1, please copy that to your script file too.]

```matlab
dvdx = ? ;
dudy = ?;
zeta = ?;
totalVort = ?;

f2 = figure;
contourf(LON(2:end-1, 2:end-1), LAT(2:end-1, 2:end-1), totalVort*1e4, (-4:0.25:4) , 'LineColor', 'none');
colormap('jet')
caxis([-4, 4])
pbaspect([lon(end-1)-lon(2)  lat(end-1)-lat(2) 1])
xlabel('longitude')
ylabel('latitude')
set(gca, 'FontSize', 14)
grid on
hold on
[C, h] = contour(LON(2:end-1, 2:end-1), LAT(2:end-1, 2:end-1), Z500(2:end-1, 2:end-1), (4900:100:5900), 'LineColor', 'k');
clabel(C, h, 'FontSize', 14, 'LabelSpacing', 300)
title('500 hPa Geopotential Height (Conoturs, m) and Vorticity (Color, 10^{-4}s^{-1})')
colorbar
hold off
```



