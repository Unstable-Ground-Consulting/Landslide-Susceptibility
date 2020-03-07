---
layout: post
title: "Creating Layers"
date: 2020-02-24
---
# Data Collection
A lot of work was done in the research and data preperation this week. A major goal of this week was to find usable data for Albania, focusing on DEMs, boundaries, roads, and buildings.

### Roads, Buildings, and Boundaries

The data for Albania was downloaded from [Albania GIS Home](http://gis.tpginc.net/albania/), although not the most promising looking the data is there. Initially, we wanted to use the government's [official site](https://geoportal.asig.gov.al/map/?themeId=3288398&auto=true), but all of their maps and layers are web based and cannot be analized with other data.

### DEMS
The DEMs aquired were through the EU's [Copernicus Land Monitering Service](https://land.copernicus.eu/). The DEMs were aquired through a tiling system so we had to figure out a way to stich the two DEMs together. After some research, we found the Mosaic to New Raster Tool which suited our purposes nicely.

[Mosaic To New Raster Tool](https://pro.arcgis.com/en/pro-app/tool-reference/data-management/mosaic-to-new-raster.htm)
/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

  The tool used to put the rasters together was the _mosaic to new raster tool_ which stiches the mosaics together and creates a new feature out of them. 
In addition to stiching them together it also has options to deal with overlapping cells.
  
  NOTE:Just be aware that you need to set the pixel type equal to what your original rasters were or else it will simplify or remove your values in the cells.
  
/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
  
After stitching the DEMs into one, we used the [Extract by Mask](https://pro.arcgis.com/en/pro-app/tool-reference/spatial-analyst/extract-by-mask.htm) tool using Albania's boundary to get the DEM of Albania. 

### Soil Maps
  Aquiring Soil data for Albania was proving to be a tougher challenge than the other data as Albania does not have extensive GIS data that can be downloaded. We were able to aquire semi-recent soil maps in pdf form, but the rigor to hand-georeference that map would be tool long for the entirety of Albania.
 
 *NOTE:* There will be a margin of error in the soil map as 
 
   _a.)_ The map will have to be georefernced by hand
  
  _b.)_ The soil data has to be transcribed from WRB to USCS in order to get the variables needed for the [CRTH model](https://github.com/Unstable-Ground-Consulting/Landslide-Susceptibility/blob/master/models/)
 
 This led us to change the scale of the project into something more manageable for the limited time we possessed.
# NEW Parameters

It came to our attention that for the time-frame needed the scope of our project needed to be more limited. Therefore, Instead of looking at countries at a whole we will be looking at specific cities, this also lets us get more into the ethical and cultural aspects and impacts of these maps.

For the United States we will be looking at Willits, California as it is one of the cities that has had numerous landslides in the past according to the United States Landslide inventory.

For Albania we chose the capital city of Tirana as it has important sites that the country would want to protect.

For both of these we used the same scope, about a 10km buffer around each

### Willits
For Willits all the DEM and Soil Map data was extracted to that 10km buffer. The remaining tasks are to translate the soil data from USGS and find the road and building data.

### Tirana
All of the data has been extracted to that extent, buildings, DEM, Soil map, and roads. The Soil Map has been georeferenced as well as a raster created of the data set for that extent. The remaining thing to do is translate that into vaules useful for the models.
