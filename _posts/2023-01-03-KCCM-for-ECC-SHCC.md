---
layout: post
title: "Calibration of KCC Model for ECC/SHCC (FE Method)"
excerpt: "An improved calibration of Karagozian & Case concrete/cementitious model for strain-hardening fibre-reinforced cementitious composites under explosion and penetration loadings"
tags: 
  - LS-DYNA
  - KCC
  - FE
---
The ultra-high tensile capacity of strain-hardening fibre-reinforced cementitious composites makes them promising for impact dynamics applications, however, there is a lack of reference for taking the parameters of the constitutive model of materials in numerical simulations. In this study, the Karagozian & Case concrete/cementitious model parameters for strain-hardening fibre-reinforced cementitious composites were comprehensively and systematically calibrated. Multiaxial behaviour, crack-bridging constitutive relations, strain-rate effects, regularization of damage evolution parameters, and parameters scaling method for wide-range strength of materials were all considered and carefully discussed. The calibrated parameters were validated using low-velocity drop-weight impact tests, near-field explosion tests, and high-speed penetration tests. In this study, the traditional element erosion method and meshless/particle methods of Smoothed Particle Galerkin (SPG) method were used for failure analysis in penetration and explosion models. The results show that the calibrated parameters accurately predict the cratering and scabbing diameters and failure modes of explosion tests with the element erosion method. Furthermore, the residual velocity of the projectile and crack patterns of targets were also predicted with good precision with both element erosion and SPG methods. However, in the simulations of low-velocity impact tests, the predictions of maximum deflection were acceptable, and the errors in residual deflection were significant due to the inherent weakness of the material constitutive model.

Please Cite: **Yin et al. (2023)**

X. Yin, Q. Li, B. Chen, S. Xu, An improved calibration of Karagozian & Case concrete/cementitious model for strain-hardening fibre-reinforced cementitious composites under explosion and penetration loadings, Cem. Concr. Compos. 137 (2023) 104911. 

[doi:10.1016/j.cemconcomp.2022.104911](https://doi.org/10.1016/j.cemconcomp.2022.104911)

### KCC Model Parameters for ECC/SHCC

```
*KEYWORD
*COMMENT
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
|      Karagozian & Case Concrete/Cementitious Model Parameters for UHTCC      |
|                        Only for Finite Element Method                        |
|                                  kg - m - s                                  |
|           Calibrated by YIN Xing - Zhejiang University (Dec, 2022)           |
|                         Contact: yinxing@zju.edu.cn                          |
| Reference                                                                    |
|    Yin X, Li Q, Chen B, Xu S. An improved calibration of Karagozian & Case   |
|        concrete/cementitious model for strain-hardening fibre-reinforced     |
|        cementitious composites under explosion and penetration loadings.     |
|        Cem Concr Compos 2023;137:104911.                                     |
|            doi: 10.1016/j.cemconcomp.2022.104911                             |
| Note: MAT ID is 72001, DIF ID is 72, EOS ID is 72                            |
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
MMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMWk:oXMMMMMM
MMMMMMMMMMWKkKWMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMWKx:,dNMMMMMM
MMMMMMMMMMXd::oKWMMMMMMMMMMMN00NMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMWKkOx:lXMMMMMMM
MMMMMMMMMWOxKk;:OWMMMMMMMMW0c',xWMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMNOxkXWO:xWMMMMMMM
MMMMMMMMMKdO0c,::oKWMMMMW0o:oc.oNMMMMMMMMMMMMMMMMMMMMN0XMMMMMXkoxKWMWkcOMMMMMMMM
MMMMMMMMNxdd;:ONO::OWMW0o;cONx'lNMMMMMMMMMMMMMMMMMMMMXllXMMXxld0WMMMNocKMMMMMMMM
MMMMMMMWOc:;c0WMW0c;x0d;:ONMMk'cXMMMMMMMMMMMMMMMMMMMMWd:OXxllxkxKWMMXlcXMMMMMMMM
MMMMMMMKc':kNN0xdk0l'',okk0WWx'lNMMMMMMMMMMMMMMMMMMMMWk;:cool;'c0WMMKclXMMMMMMMM
MMMMMMXo';dxoc,.,ox:..,:,'oXXo.cXMMMMMMMMMMMMMMMMMMMMWd';ONOc,:oox00d,,llokXMMMM
MMMMMNd'.,lddc,:l:'';coc;:oc;''oXXkdOWMMMMMMMMMMMMMMMWk:;oo;..':ooc,...,:lxXMMMM
MMMMNd;lxOKOc',;'.,;xKd;,,,cxOOOd:;o0WMMMMMMMMMMMMMMMMWO:.':;.:dxoc;coOKNWMMMMMM
MMMWk,lXWx:,,;,'cl,'::,;lx0NKkl;ckXWMMMMMMMMMMMMMMMWXkdooddd:';coxOXWMMMMMMMMMMM
MMMK::kkl,;dOo:dOl',;''lxxo:,':kNMMMMMMMMMMMMMMMMN0xoodddlc;';ONNK0XWMMMMMMMMMMM
MMWOc:lol;oNWK0Oc.;OXOdl,...,dXMMMMMMMMMMMMMMMWKkolcclcldOKd,;ooc,'lXMMMMMMMMMMM
XkoclxKWKcoNMWk:''lXMWKd,'::;:ldk0XWMMMMMMMMW0o:;:coxOXWKdl::oxkc';OWMMMMMMWKxoo
dokKWMMMNolKXd,:o;cxxc,,lONNKkdc:;:cldkNMWKxc,;lx0XWMMMMXOk0NWNd,:0WMMWX0ko:,;oO
WWMMMMMMMKdoc:dKNkc;:lkKWMMMMMMWNKOxdll0WXxodOXWMMMMMMMMMMMMMMO;'cddooc:::cokXWM
MMMMMMMMMMWK0KWMMWXKXWMMMMMMMMMMMMMMMWWMMMWWMMMMMMMMMMMMMMMMMMXxc;;:clox0XWMMMMM
$--------------------------------Input Paramters--------------------------------
$ le      Element Size (m)
$ fc      Unconfined Uniaxial Compressive Strength (MPa)
$ ft      Unconfined Uniaxial Tensile Strength (Pa)
$ ro      Mass Density (kg/m^3)
$ pr      Poisson’s Ratio
$ omega   Associativity Parameter (ω), and ω = 1 and 0 represent the associated 
$         and non-associated flow rule. Do not change the calibrated value of
$         0.75 unless there are confinement.
$-------------------------------------------------------------------------------
*KEYWORD
*PARAMETER_EXPRESSION
$#    prmr                                                            expression
Rle       0.0025
Rfc       50.00
Rft       5.0e+6
Rro       2000.0
Rpr       0.255
Romega    0.75
$-------------------------------------------------------------------------------
$*                           Parameters Calculation                            *
$-------------------------------------------------------------------------------
Rb1       1.0
Rb2       2.68*log(&le*1000)-14.05
Rb3       0.05
RLW       0.8*&le
RSle      &le/0.01
$----------------------------------ETA-LAMBDA-----------------------------------
$----------------------------------LAMBDA (λ)-----------------------------------
Rlambda02 1.00E-04
Rlambda03 3.00E-04
Rlambda04 5.00E-04
Rlambda05 6.50E-04
Rref      &lambda05
Rlambda06 &lambda05+(7.00E-04-&lambda05)*&Sle
Rlambda07 &lambda05+(8.00E-04-&lambda05)*&Sle
Rlambda08 &lambda05+(1.00E-03-&lambda05)*&Sle
Rlambda09 &lambda05+(1.25E-03-&lambda05)*&Sle
Rlambda10 &lambda05+(1.75E-03-&lambda05)*&Sle
Rlambda11 &lambda05+(3.00E-03-&lambda05)*&Sle
$-----------------------------------LAMBDA->1-----------------------------------
Rl02      &lambda02/&ref
Rl03      &lambda03/&ref
Rl04      &lambda04/&ref
Rl05      &lambda05/&ref
Rl06      &lambda06/&ref
Rl07      &lambda07/&ref
Rl08      &lambda08/&ref
Rl09      &lambda09/&ref
Rl10      &lambda10/&ref
Rl11      &lambda11/&ref
$------------------------------------ETA (η)------------------------------------
Reta02    0.51
Reta03    0.88
Reta04    0.98
Reta05    1.00
Reta06    0.81
Reta07    0.55
Reta08    0.32
Reta09    0.22
Reta10    0.13
Reta11    0.06
$----------------------------Equation of State (EOS)----------------------------
RSs       (&fc/50.00)**0.638
Rc2       1.856895e+07*&Ss
Rc3       4.048031e+07*&Ss
Rc4       6.499132e+07*&Ss
Rc5       1.234835e+08*&Ss
Rc6       1.862465e+08*&Ss
Rc7       2.642361e+08*&Ss
Rc8       4.042460e+08*&Ss
Rc9       2.360113e+09*&Ss
Rc10      3.609804e+09*&Ss
Rk1       1.237930e+10*&Ss
Rk2       1.237930e+10*&Ss
Rk3       1.255261e+10*&Ss
Rk4       1.318395e+10*&Ss
Rk5       1.568457e+10*&Ss
Rk6       1.819757e+10*&Ss
Rk7       2.069819e+10*&Ss
Rk8       2.259222e+10*&Ss
Rk9       5.082940e+10*&Ss
Rk10      6.189650e+10*&Ss
$-------------------K&C strength surface parameters for UHTCC-------------------
Ra0m      0.50927*&fc*10**6
Ra1m      0.65165
Ra2m      0.08228/&fc/10**6
Ra0y      0.33365*&fc*10**6
Ra1y      1.17451
Ra2y      0.20506/&fc/10**6
Ra1r      0.60586
Ra2r      0.07977/&fc/10**6
*DEFINE_CURVE_TITLE
DIF_UHTCC
$#    lcid      sidr       sfa       sfo      offa      offo    dattyp     lcint
        72         0       1.0       1.0       0.0       0.0         0         0
$#                a1                  o1  
   -3.0000000000e+07            9.948667
            -3000000            9.841416
           -300000.0            9.522056
            -30000.0            8.657233
             -3000.0            6.812797
              -300.0            4.315611
              -100.0            3.276448
               -30.0            2.414954
               -10.0            1.879336
                -3.0            1.506715
                -1.0            1.301248
                -0.1             1.09859
               -0.01            1.031767
              -0.001            1.010184
   -9.9999997474e-05             1.00326
   -9.9999997474e-06            1.001043
                 0.0                 1.0
    9.9999997474e-06                 1.0
    9.9999997474e-05            1.000003
               0.001             1.00002
                0.01            1.000143
                 0.1            1.001015
                 1.0            1.007186
                 3.0            1.018205
                10.0             1.04992
                30.0            1.122447
               100.0            1.307575
               300.0             1.63294
              3000.0            2.533467
             30000.0            2.917814
            300000.0               2.988
             3000000            2.998301
    3.0000000000e+07             2.99976
*MAT_CONCRETE_DAMAGE_REL3_TITLE
KCC_UHTCC_FE
$#     mid        ro        pr  
     72001&ro       &pr       
$       ft        A0        A1        A2        B1     OMEGA       A1F
$#      ft        a0        a1        a2        b1     omega       a1f   
&ft       &a0m      &a1m      &a2m      &b1       &omega    &a1r      
$  sLambda      NOUT     EDROP     RSIZE       UCF    LCRate  LocWidth      NPTS
$# slambda      nout     edrop     rsize       ucf    lcrate  locwidth      npts
       0.0       2.0       1.0     39.371.45000E-4        72&lw             13.0
$ Lambda01  Lambda02  Lambda03  Lambda04  Lambda05  Lambda06  Lambda07  Lambda08
$# lambda1   lambda2   lambda3   lambda4   lambda5   lambda6   lambda7   lambda8
       0.0&lambda02 &lambda03 &lambda04 &lambda05 &lambda06 &lambda07 &lambda08 
$ Lambda09  Lambda10  Lambda11  Lambda12  Lambda13        B3       A0Y       A1Y
$#lambda09  lambda10  lambda11  lambda12  lambda13        b3       a0y       a1y
&lambda09 &lambda10 &lambda11       0.011.00000E10&b3       &a0y      &a1y      
$    Eta01     Eta02     Eta03     Eta04     Eta05     Eta06     Eta07     Eta08
$#    eta1      eta2      eta3      eta4      eta5      eta6      eta7      eta8
       0.0&eta02    &eta03    &eta04    &eta05    &eta06    &eta07    &eta08    
$    Eta09     Eta10     Eta11    Eta012     Eta13        B2       A2F       A2Y
$#   eta09     eta10     eta11     eta12     eta13        b2       a2f       a2y
&eta09    &eta10    &eta11           0.0       0.0&b2       &a2r      &a2y      
*EOS_TABULATED_COMPACTION
$    EOSID     Gamma        E0      Vol0
$#   eosid      gama        e0        vo       lcc       lct       lck      lcid
        72       0.0       0.0       1.0         0         0         0         0
$    VolStrain01     VolStrain02     VolStrain03     VolStrain04     VolStrain05
$#           ev1             ev2             ev3             ev4             ev5
             0.0         -0.0015         -0.0043         -0.0101         -0.0305
$    VolStrain06     VolStrain07     VolStrain08     VolStrain09     VolStrain10
$#           ev6             ev7             ev8             ev9            ev10
         -0.0513         -0.0726         -0.0943          -0.174          -0.208
$     Pressure01      Pressure02      Pressure03      Pressure04      Pressure05
$#            c1              c2              c3              c4              c5
             0.0&c2             &c3             &c4             &c5             
$     Pressure06      Pressure07      Pressure08      Pressure09      Pressure10
$#            c6              c7              c8              c9             c10
&c6             &c7             &c8             &c9             &c10            
$            Multipliers of Gamma*E
$#            t1              t2              t3              t4              t5
             0.0             0.0             0.0             0.0             0.0
$#            t6              t7              t8              t9             t10
             0.0             0.0             0.0             0.0             0.0
$     BulkUnld01      BulkUnld02      BulkUnld03      BulkUnld04      BulkUnld05
$#            k1              k2              k3              k4              k5
&k1             &k2             &k3             &k4             &k5             
$     BulkUnld06      BulkUnld07      BulkUnld08      BulkUnld09      BulkUnld10
$#            k6              k7              k8              k9             k10
&k6             &k7             &k8             &k9             &k10            
*END
```
