## Atmospheric Dynamics I

**Problem 2 is a homework assignment**. 

Data for today's exercises and homework can be downloaded from Canvas or 
[Sharepoint](https://gohkust-my.sharepoint.com/:u:/g/personal/shixm_ust_hk/EX8qpWmNIClFic5OzIdtQx4BKxOqla_o56CIg_e6M3YeWg?e=67f33u)

### Problem 1 Geopotential Height and Pressure Gradient Force

`Z` in the dataset is geopotential height. Please complete the code below to calculate pressure gradient force and plot it along with geopotential height.

#### Step 1 Height Contours
```matlab
%% load data
load Lab9Data.mat
% create grid mesh
[X, Y] = meshgrid(lon, lat);

%% plot contours of geopotential height
f1 = figure;
[C, h] = contour(X, Y, Z, (4900:100:5900), 'LineColor', 'k');
clabel(C, h, 'FontSize', 12, 'LabelSpacing', 300)
grid on
xlabel('longitude')
ylabel('latitude')
set(gca, 'FontSize', 18)
```

#### Step 2 Pressure Gradient Force
```matlab
%% calculate pressure gradient force
hy = 6.37e6 * (1* pi/180);
hx = ?;   % hx is a function of latitude, but here use the value at 30 degree north

[Zx, Zy] = gradient(Z, hx, hy);

Px = ?;
Py = ?;
P = ?;   % what is the total magnitude of the force?

f2 = figure;
contourf(X, Y, P, (0:0.0005:0.0060), 'LineColor', 'none')
colormap('cool')
colorbar
caxis([0.0 0.006])
hold on
[C, h] = contour(X, Y, Z, (4900:100:5900), 'LineColor', 'k');
clabel(C, h, 'FontSize', 12, 'LabelSpacing', 300)
grid on
xlabel('longitude')
ylabel('latitude')
set(gca, 'FontSize', 18)
hold off
```

### Problem 2 Distribution of Wind Speed

`u` and `v` in the dataset are the east-west and north-west components of wind (vectors). Please 
* _**calculate wind speed and display it as color shading.**_
* _**compare the figure you get here with the one from Problem 1, and describe the relation between pressure gradient force and wind speed**_

```matlab
%% Plot wind vectors and speed; overlay the maps
spd = ?;

f3 = figure;
contourf(?, ?, ?, (1:70), 'LineColor', 'none')

colormap('cool')
colorbar
caxis([1 70])
hold on
[C, h] = contour(X, Y, Z, (4900:100:5900), 'LineColor', 'k');
clabel(C, h, 'FontSize', 12, 'LabelSpacing', 300)
% plot wind vectors too
quiver(X(1:4:end,1:4:end), Y(1:4:end,1:4:end), u(1:4:end,1:4:end), v(1:4:end, 1:4:end), ...
    'Color', 'black', 'LineWidth', 1);
grid on
xlabel('longitude')
ylabel('latitude')
ylim([0 60])
xlim([140 240])
set(gca, 'FontSize', 18)
hold off
```
