---
layout: default
title: "Models"
---

## Models Used For Landslide Susceptibility

### *Critical Rainfall Threshold Model* (Eq. 28, [Iverson, 2000](https://agupubs.onlinelibrary.wiley.com/doi/abs/10.1029/2000WR900090))
```
     tan φ       C - ψt * γw * (tan φ)
Fs = -----  +  --------------------------
     tan θ     γr * H * (sin θ) * (cos θ)
```

Fs= Factor of Safety

φ = Internal Angle of Friction

θ = Hillslope

C = Soil Cohesion

ψt = Pressure Head

γw = Unit Weight of Water

γr = Unit Weight of Soil Regolith

H = Depth of Soil Regolith


This model is designed to predict the infiltration of rainfall into the landscape. It measures the sliding forces and the retention forces, basically the forces that cause the land to slide and the forces that keep the land in place. If these forces are balanced the smaller likelyhood that the land will become a landslide and the opposite is true, if the forces are unbalanced then the land is more likely to become a landslide.

Its output is called the Factor of Safety which is a number between 0-1. The closer to 1 the number is the more stable the land is and less likely to form a landslide. Likewise if the number is closer to 0 the more unstable the land is and is more likely to become a landslide.

An issue with this iteration of the formula is that there seems to be spots that become areas of no data after being put thorugh this calcuation. This creates gaps in the data that cannot be used in further analyses, which could be problematic for others who want to put these susceptibility models into more analysis. In addition this formula creates valuse far greater than the standard 0-1 for the factor of safety making the values vary greatly beyond the stated limits.

### [*The Infinite Slope Model of FS*](https://www.sciencedirect.com/science/article/pii/S0169555X11001218)

_From:_
Jason N. Goetz, Richard H. Guthrie, Alexander Brenning,
Integrating physical and empirical landslide susceptibility models using generalized additive models,
Geomorphology,
Volume 129, Issues 3–4,
2011,
Pages 376-386,
ISSN 0169-555X,
https://doi.org/10.1016/j.geomorph.2011.03.001.

```
     C + cosθ * (1 − min( R/T * a/sinθ, 1) / r) * tanφ
FS= ---------------------------------------------------
                            sinθ
```
C = dimensionless cohesion

R = steady state recharge (mh^-1)

T = Soil Transmissivity (m^2 h^-1)

a = specific cachement area in meters, which isthe catchment area (m2) divided by the contour length or width of agrid cell (m)

θ = local slope

φ = friction angle describing instablility

r = the ratio of the saturated bulk density of soil to the density of water (ρs/ρw)

The entire section of (T/R)sinθ is the length of a hillslope required to reach saturation.

Similar to the Critical Rainfall Threshold Model, the Infinite Slope Model of FS is a ratio of stabilizing forces and destabilizing forces. This equation is actually dirived from the [SHALSTAB model](https://www.sciencedirect.com/science/article/pii/S0169555X06003515) which is the FS model combined with a hydrology model. From the article by Goetz et all. FS was considered more effective in thier comparison using training data over the SHALSTAB model.
```
NOTE: More Information about the SHALSTAB model can be found here
C. Meisina, S. Scarabelli, A comparative analysis of terrain stability models for predicting shallow landslides in colluvial soils, Geomorphology, Volume 87, Issue 3, 2007, Pages 207-223, ISSN 0169-555X, https://doi.org/10.1016/j.geomorph.2006.03.039. (http://www.sciencedirect.com/science/article/pii/S0169555X06003515)
```
