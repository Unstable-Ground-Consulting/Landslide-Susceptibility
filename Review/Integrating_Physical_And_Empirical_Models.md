---
layout: default
title: "Review of Integrating physical and empirical landslide susceptibility models using generalized
additive models"
---

[Integrating physical and empirical landslide susceptibility models using generalized
additive models](https://www-sciencedirect-com.proxy.wm.edu/science/article/pii/S0169555X11001218)

   This article by Jason Goetz, Richard Guthrie, and Alexander Brenning is useful for us in several specific ways. The first is outlined in their introduction, “Since many of the regions that are most highly susceptible to landslides are in developing countries, it is important to develop methods that are affordable and can perform well with little data (Sidle and Ochiai, 2006).” Creating a useful landslide analysis that doesn’t require too much data could be useful in disadvantaged communities that don’t have the resources to actively create data for these analyses. 

   What is interesting and disappointing is that they don’t include such a disadvantaged area in their research. Instead they focus on an area of Canada, this is so they can work with more data to test the theory, but it would have been a stronger message if they could show it working in areas with little to no data. It just seems like their claiming something without showing that it can be done.

  The second reason is built off the first in that the models they are testing are physically-based and can be run from mostly the DEM. The SHALSTAP and FS model, SHALSTAB focuses on the slope itself and determines how much steady rainfall would cause such a slope to fail, focusing on the topography as a dominate force in landslides. Instead of giving exact numbers it categorizes the landscape into Unconditionally Stable, Conditionally Stable, Unconditionally Unstable, etc. One issue of this model described by the authors is that it does not fully capture the effects of cohesion in the model.  The FS model is a comparison of stabilizing and destabilizing forces to determine landslide susceptibility, like the Critical Rainfall Threshold model we are using. The Empirical methods are the generalized additive model (GAM) and generalized linear model (GLM).  They use the GLM a sit is widely used for such predictive mapping, while GAM is a relatively new model for landslide mapping. 

  After combining the approaches, the authors realized that although SHALSTAP may be good at identifying areas of issues it too often would classify large areas to be unstable, which they found to be a problem especially in terms of land use. FS proved to be better suited for more specificity, as well as the GAM. Although the authors did not seem to see too much of a difference between GAM and GLM. This article has some good ideas in the terms of determining the accuracy of models, which could be useful in the future after we do some more analysis. It’s breakdown of SHALSTAP and FS were useful so we will take a look at what those can do in our projects that have less data than we are used to.
