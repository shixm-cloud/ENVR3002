## Radiation I

### Problem 1 Outgoing Longwave Radiation

Observed data of outgoing longwave radiation (OLR) for a weather event is provided on Canvas. You will explore this data to understand how remote sensing works.

Firstly, let's load and take a look at the data
```
% load data 
load OLR1.mat 
% look at what we have 
f1 = figure;
contourf(olr, (75:10:305), 'LineColor', 'none')
colormap("jet")
colorbar
caxis([75 305]);
title('Outgoing Longwave Radiation (OLR; W m^{-2})')
hold on
contour(landmask, [0.5 0.5]) 
hold off
```
Running this code in MATLAB/OCTAVE, you should see the figure below,
![OLR](OLR1.png)

Now please calculate the equivalent blackbody temperature and plot it
```
[FILL YOUR OWN CODE HERE AND SAVE AS 'T']

f2 = figure;
contourf(T, (190:5:270), 'LineColor', 'none')
colormap("jet")
colorbar
caxis([190 260]);
title('Equivalent Blackbody Temperature (K)')
hold on
contour(landmask, [0.5 0.5]) 
hold off
```

