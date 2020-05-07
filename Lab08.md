## Cloud Physics II

### Problem 1. Temperature and Cloud Water and Ice

Please download the data file [Lab8Data.mat](Lab8Data.mat) first. This file contains azimuthally averaged data from a tropical cyclone. You will plot the distribution of temperature, cloud water and ice, and vertical velocity to investigate the structure of a tropical cyclone.

```matlab
[FILL YOUR CODE HERE TO LOAD THE DATA]

%% plot temperature and liquid cloud water
f1 = figure;
[X, Z] = meshgrid(x, z);
%[REPLACE ? BELOW WITH YOUR VARIABLE TO MAKE COUNTOUR PLOT OF CLOUD WATER MIXING RATIO IN g/kg]
contourf(X, Z, ?, (0:0.025:0.4), 'LineColor', 'none')

caxis([0, 0.4])
colormap(flipud(gray))
colorbar;
hold on
%[REPLACE ? BELOW WITH YOUR VARIABLE TO MAKE COUNTOUR PLOT OF Temperature IN DEGREE CELSIUS]
[C h] = contour(X, Z, ?, (-80:10:20), 'LineColor', 'red');

clabel(C, 'FontSize', 14, 'Color', 'red')
hold off
xlim([2 150])
xlabel('distance from tropical cyclone center (km)')
ylabel('height (km)')
title('liquid cloud water mixing ratio (g/kg) and temperature ({\circ}C)')

%% plot temperature and ice cloud water
f2 = figure;
[X, Z] = meshgrid(x, z);
%[REPLACE ? BELOW WITH YOUR VARIABLE TO MAKE COUNTOUR PLOT OF CLOUD ICE MIXING RATIO IN g/kg]
contourf(X, Z, ?, (0:0.025:0.4), 'LineColor', 'none')
caxis([0, 0.4])
colormap(flipud(gray))
colorbar;
hold on
%[REPLACE ? BELOW WITH YOUR VARIABLE TO MAKE COUNTOUR PLOT OF Temperature IN DEGREE CELSIUS]
[C h] = contour(X, Z, ?, (-80:10:20), 'LineColor', 'red');

clabel(C, 'FontSize', 14, 'Color', 'red')
hold off
xlim([2 150])
xlabel('distance from tropical cyclone center (km)')
ylabel('height (km)')
title('ice cloud water mixing ratio (g/kg) and temperature ({\circ}C)')
```

_Do you see the existance of supercooled water? In what temperature range do you see them?_


### Problem 2. Vertical Motions and Clouds<sup>*</sup>

_**<sup>*</sup>This is a homework assignment. For this one, you do NOT need to submit your code. However your answer to the homework question below will be based on the plot you get, thus you still need to complete the code to obatin the figure**_

Now please complete the code below to plot vertical velocity contours and the distribution of cloud water and ice mixing ratios. Answer this **homework questions**:
* _**In the figure you get, do you see cloud water and ice appear in regions with ascending regions or descending regions? Why that can cause cooling of the air and thereby the formation of clouds?**_

```matlab
%% plot vertical velocity and liquid+ice cloud water
f3 = figure;
[X, Z] = meshgrid(x, z);
[REPLACE ? WITH A VARIABLE FOR THE TOTAL MIXING RATIO OF CLOUD WATER+ICE]
contourf(X, Z, ?, (0:0.025:0.4), 'LineColor', 'none')

caxis([0, 0.4])
colormap(flipud(gray))
colorbar;
hold on
[REPLACE ? BELOW TO PLOT CONTOURS OF VERTICAL VELOCITIES]
[C h] = contour(X, Z, ?, (-3.5:1:3.5), 'LineColor', 'red');

clabel(C, 'FontSize', 14, 'Color', 'red')
hold off
xlim([2 150])
xlabel('distance from tropical cyclone center (km)')
ylabel('height (km)')
title('liquid+ice cloud water mixing ratio (g/kg) and vertical velocity (m/s)')

```



