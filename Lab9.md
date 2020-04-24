## Atmospheric Dynamics I

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


