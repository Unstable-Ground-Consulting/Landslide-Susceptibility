---
layout: post
title: "Creating Layers"
date: 2020-02-24
---

A lot of work was done in the research and data preperation this week. A major goal of this week was to find usable data for Albania, focusing on DEMs, boundaries, roads, and buildings.

The DEMs aquired were through the EU's [Copernicus Land Monitering Service](https://land.copernicus.eu/). The DEMs were aquired through a tiling system so we had to figure out a way to stich the two DEMs together.

ENTER MOSAIC TOOLS
  The tool used to put the rasters together was the [_mosaic to new raster tool_](https://pro.arcgis.com/en/pro-app/tool-reference/data-management/mosaic-to-new-raster.htm) which stiches the mosaics together and creates a new feature out of them. In addition to stiching them together it also has options to deal with overlapping cells.
  
