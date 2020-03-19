---
layout: default
title: "Models"
---

## Models Used For Landslide Susceptibility

### *Critical Rainfall Threshold Model* (Eq. 28, Iverson, 2000)
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


This model is designed to predict the infiltration of rainfall into the landscape. 

### [*FR*](https://www.mdpi.com/2073-4441/11/7/1402)

FR is the Frequency Ratio bivariate model that focuses on the possibility of occurance for a given characteristic. The larger FR is the higher occurance of landslides and a higher correlation with the factors creating them, the lower the number the safer the area. 
```
The Base Model
        *FLij*
Wij = ---------
        FNij
```
