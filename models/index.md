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

### [*FR*](https://www.mdpi.com/2073-4441/11/7/1402)

FR is the Frequency Ratio bivariate model that focuses on the possibility of occurance for a given characteristic. The larger FR is the higher occurance of landslides and a higher correlation with the factors creating them, the lower the number the safer the area. 
```
The Base Model
        FL ij
W ij = ---------
        FN ij
```
W = FR = the weights
