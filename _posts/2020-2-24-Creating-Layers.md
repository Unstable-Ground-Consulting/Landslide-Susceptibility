---
layout: post
title: "Creating Layers"
date: 2020-02-24
---
### Data Collection
A lot of work was done in the research and data preperation this week. A major goal of this week was to find usable data for Albania, focusing on DEMs, boundaries, roads, and buildings.

## DEMS
The DEMs aquired were through the EU's [Copernicus Land Monitering Service](https://land.copernicus.eu/). The DEMs were aquired through a tiling system so we had to figure out a way to stich the two DEMs together. After some research, we found the Mosaic to New Raster Tool which suited our purposes nicely.

[Mosaic To New Raster Tool](https://pro.arcgis.com/en/pro-app/tool-reference/data-management/mosaic-to-new-raster.htm)
```
  The tool used to put the rasters together was the _mosaic to new raster tool_ which stiches the mosaics together and creates a new feature out of them. 
In addition to stiching them together it also has options to deal with overlapping cells.
  
  NOTE:Just be aware that you need to set the pixel type equal to what your original rasters were or else it will simplify or remove your values in the cells.
```
After stitching the DEMs into one, we used the [Extract by Mask](https://pro.arcgis.com/en/pro-app/tool-reference/spatial-analyst/extract-by-mask.htm) tool using Albania's boundary to get the DEM of Albania. 

### Soil Maps
  Aquiring Soil data for Albania was proving to be a tougher challenge than the other 
### NEW Parameters
```
It came to our attention that for the time-frame needed 
```
