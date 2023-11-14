---
layout: post
title: "Strength Surface of KCC Model"
excerpt: "An improved calibration of Karagozian & Case concrete/cementitious model for strain-hardening fibre-reinforced cementitious composites under explosion and penetration loadings"
tags: 
  - MATLAB
  - KCC
---
Please Cite: **Yin et al. (2023)**

X. Yin, Q. Li, B. Chen, S. Xu, An improved calibration of Karagozian & Case concrete/cementitious model for strain-hardening fibre-reinforced cementitious composites under explosion and penetration loadings, Cem. Concr. Compos. 137 (2023) 104911. 

[doi:10.1016/j.cemconcomp.2022.104911](https://doi.org/10.1016/j.cemconcomp.2022.104911)

### Strength Surface of KCC Model (by MATLAB)

```
clear;
clc;
close all;
m = 500;
n = 500;
mm =6*m-5;
% K&C parameters
fc = 45.40;
fyc = 20.36;
ft = 3.8274;
a0 = 13.42;
a1 = 0.4463;
a2 = 0.001780;
a0y = 10.13;
a1y = 0.625;
a2y = 0.005676;
a1r = 0.4417;
a2r =0.002608;
pmin = -3*ft;
pmax = 200;
alpha = 1.15;
eta = 1.0;
% polar angle [0, 2*pi]
phi = linspace(0, 2*pi, mm);
% lode angle
ith1 = linspace(0, pi/3, m);
ith2 = linspace(pi/3, 0, m);
th1 = ith1(2:end);
th2 = ith2(2:end);
th = [ith1, th2, th1, th2, th1, th2];
% hydrostatic stress
p = linspace(pmin, pmax, n);
% create grids
Aphi = repmat(phi, n, 1);
Ath = repmat(th, n, 1);
P = repmat(p', 1, mm);
% Tensile-Compressive Meridian Ratio
psi_p = linspace(pmin, pmax, n);
psi(1,n) = 0;
for x = 1:n
    if (psi_p(1,x)<=0.0)
        psi(1,x) = 0.5;
    elseif (psi_p(1,x) > 0 && psi_p(1,x) <= fc/3)
        psi(1,x) = 0.5 + (0.5+1.5*ft/fc-0.5)*((psi_p(1,x)-0.0)/(fc/3-0.0));
    elseif (psi_p(1,x) > fc/3 && psi_p(1,x) <= 2*alpha*fc/3)
        psi(1,x) = 0.5+1.5*ft/fc + (alpha*fc/(a0+(2*alpha*fc/(3*a1+2*a2*alpha*fc))) - (0.5+1.5*ft/fc))*((psi_p(1,x)-fc/3)/(2*alpha*fc/3-fc/3));
    elseif (psi_p(1,x) > 2*alpha*fc/3 && psi_p(1,x)<= 3*fc)
        psi(1,x) = alpha*fc/(a0+(2*alpha*fc/(3*a1+2*a2*alpha*fc))) + (0.753-alpha*fc/(a0+(2*alpha*fc/(3*a1+2*a2*alpha*fc))))*((psi_p(1,x)-2*alpha*fc/3)/(3*fc-2*alpha*fc/3));
    elseif (psi_p(1,x)>3*fc && psi_p(1,x)<8.45*fc)
        psi(1,x) = 0.753 + (1 - 0.753)*((psi_p(1,x)-3*fc)/(8.45*fc-3*fc));
    elseif (psi_p(1,x)>=8.45*fc)
        psi(1,x) = 1.0;
    end
end
% K&C strength surface
% Maximum
delta_sigma_m(n,mm) = 0;
for x = 1:n
    for y = 1:mm
        if (P(x,y)>=fc/3)
            delta_sigma_m(x,y) = a0+(P(x,y)/(a1+a2*P(x,y)));
        elseif (P(x,y)<fc/3 && (P(x,y)>=0))
            delta_sigma_m(x,y) = 3*(P(x,y)+ft)/(2*psi(1,x));
        elseif (P(x,y)<=0)
            delta_sigma_m(x,y) = 3*(P(x,y)/eta + ft);
            if delta_sigma_m(x,y) < 0
                delta_sigma_m(x,y) = 0;
          end
        end
    end
end
% Yield
delta_sigma_y(n,mm) = 0;
for x = 1:n
    for y = 1:mm
        if (P(x,y)>=fyc/3)
            delta_sigma_y(x,y) = a0y+(P(x,y)/(a1y+a2y*P(x,y)));
        elseif (P(x,y)<fyc/3 && (P(x,y)>=0))
            delta_sigma_y(x,y) = 1.35*ft + 3*P(x,y)*(1-1.35*ft/fyc);
        elseif (P(x,y)<=0)
            delta_sigma_y(x,y) = 1.35*(P(x,y)+ft);
            if delta_sigma_y(x,y) < 0
                  delta_sigma_y(x,y) = 0;
            end
        end
    end
end
% Residual
delta_sigma_r(n,mm) = 0;
for x = 1:n
    for y = 1:mm
        delta_sigma_r(x,y) = P(x,y)/(a1r+a2r*P(x,y));
        if delta_sigma_r(x,y) < 0
            delta_sigma_r(x,y) = 0;
        end
    end
end
% Willam & Warnke
for x=1:n
    for y=1:mm
        e(x,y) = (2*(1-psi(1,x)*psi(1,x))*cos(th(1,y))+(2*psi(1,x)-1)*sqrt(4*(1-psi(1,x)*psi(1,x))*cos(th(1,y))*cos(th(1,y))+5*psi(1,x)*psi(1,x)-4*psi(1,x)))/(4*(1-psi(1,x)*psi(1,x))*cos(th(1,y))*cos(th(1,y))+(1-2*psi(1,x))^2);
    end
end
r_m = delta_sigma_m.*e;
X_m = r_m.*cos(Aphi-pi/6);
Y_m = r_m.*sin(Aphi-pi/6);
r_y = delta_sigma_y.*e;
X_y = r_y.*cos(Aphi-pi/6);
Y_y = r_y.*sin(Aphi-pi/6);
r_r = delta_sigma_r.*e;
X_r = r_r.*cos(Aphi-pi/6);
Y_r = r_r.*sin(Aphi-pi/6);
Z = P;
figure(1)
surf_m = surf(X_m, Y_m, Z,'FaceAlpha',0.6);
hold on;
surf_y = surf(X_y, Y_y, Z,'FaceAlpha',0.6);
hold on;
surf_r = surf(X_r, Y_r, Z,'FaceAlpha',0.6);
colormap(flipud(parula));
shading interp;
axis off;
daspect([1 1 0.5]);
view(90,0);
```
