---
layout: post
title: "Calibration of KCC Model for ECC/SHCC"
excerpt: "An improved calibration of Karagozian & Case concrete/cementitious model for strain-hardening fibre-reinforced cementitious composites under explosion and penetration loadings"
tags: 
  - KCC
---

The ultra-high tensile capacity of strain-hardening fibre-reinforced cementitious composites makes them promising for impact dynamics applications, however, there is a lack of reference for taking the parameters of the constitutive model of materials in numerical simulations. In this study, the Karagozian & Case concrete/cementitious model parameters for strain-hardening fibre-reinforced cementitious composites were comprehensively and systematically calibrated. Multiaxial behaviour, crack-bridging constitutive relations, strain-rate effects, regularization of damage evolution parameters, and parameters scaling method for wide-range strength of materials were all considered and carefully discussed. The calibrated parameters were validated using low-velocity drop-weight impact tests, near-field explosion tests, and high-speed penetration tests. In this study, the traditional element erosion method and meshless/particle methods of Smoothed Particle Galerkin (SPG) method were used for failure analysis in penetration and explosion models. The results show that the calibrated parameters accurately predict the cratering and scabbing diameters and failure modes of explosion tests with the element erosion method. Furthermore, the residual velocity of the projectile and crack patterns of targets were also predicted with good precision with both element erosion and SPG methods. However, in the simulations of low-velocity impact tests, the predictions of maximum deflection were acceptable, and the errors in residual deflection were significant due to the inherent weakness of the material constitutive model.

Please Cite: **Yin et al. (2023)**
X. Yin, Q. Li, B. Chen, S. Xu, An improved calibration of Karagozian & Case concrete/cementitious model for strain-hardening fibre-reinforced cementitious composites under explosion and penetration loadings, Cem. Concr. Compos. 137 (2023) 104911. https://doi.org/10.1016/j.cemconcomp.2022.104911.

### KCC Model Parameters for ECC/SHCC

```
*KEYWORD
*MAT_CONCRETE_DAMAGE_REL3
$HMNAME MATERIALS         3UHTCC
$#     mid        ro        pr  
         3    2000.0       0.2
$#      ft        a0        a1        a2        b1     omega       a1f   
   300000013773027.0    0.53632.0861E-09       2.4       0.5    0.5363
$# slambda      nout     edrop     rsize       ucf    lcrate  locwidth      npts
     100.0       2.0       1.0     39.371.45000E-4       111    0.0254      13.0
$# lambda1   lambda2   lambda3   lambda4   lambda5   lambda6   lambda7   lambda8
       0.08.00000E-62.40000E-54.00000E-55.60000E-57.20000E-58.80000E-53.20000E-4
$#lambda09  lambda10  lambda11  lambda12  lambda13        b3       a0y       a1y
5.20000E-45.70000E-4       1.0      10.01.00000E10      0.039988930.40    0.7349
$#    eta1      eta2      eta3      eta4      eta5      eta6      eta7      eta8
       0.0      0.85      0.97      0.99       1.0      0.99      0.97       0.5
$#   eta09     eta10     eta11     eta12     eta13        b2       a2f       a2y
       0.1       0.0       0.0       0.0       0.0     -11.32.0861E-097.9082E-09
*EOS_TABULATED_COMPACTION
$HMNAME PROPERTIES         8EOS8_72
$#   eosid      gama        e0        vo       lcc       lct       lck      lcid
         8       0.0       0.0       1.0         0         0         0         0
$    VolStrain01     VolStrain02     VolStrain03     VolStrain04     VolStrain05
  0.00000000E+00 -1.50000000E-03 -4.30000000E-03 -1.01000000E-02 -3.05000000E-02
$    VolStrain06     VolStrain07     VolStrain08     VolStrain09     VolStrain10
 -5.13000000E-02 -7.26000000E-02 -9.43000000E-02 -1.74000000E-01 -2.08000000E-01
$     Pressure01      Pressure02      Pressure03      Pressure04      Pressure05
  0.00000000E+00  4.98938467E+05  1.08768586E+06  1.74628464E+06  3.31794081E+06
$     Pressure06      Pressure07      Pressure08      Pressure09      Pressure10
  5.00435283E+06  7.09989439E+06  1.08618904E+07  6.34150792E+07  9.69936380E+07
$            Multipliers of Gamma*E 
  .000000000E+00  .000000000E+00  .000000000E+00
  .000000000E+00  .000000000E+00  .000000000E+00
$     BulkUnld01      BulkUnld02      BulkUnld03      BulkUnld04      BulkUnld05
  3.32625645E+08  3.32625645E+08  3.37282404E+08  3.54246312E+08  4.21436692E+08
$     BulkUnld06      BulkUnld07      BulkUnld08      BulkUnld09      BulkUnld10
  4.88959698E+08  5.56150078E+08  6.07041802E+08  1.36576090E+09  1.66312822E+09
*END
```
