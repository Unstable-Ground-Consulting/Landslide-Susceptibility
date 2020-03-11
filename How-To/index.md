---
layout: default
title: "How-to"
---

# ArcPro Model Builder: A Simple Guide
 This will be a simple overview of that Model Builder can do for you as a user of ArcPro, introducing you to the basics of the workflow.
  For more detailed information visit ESRI's [site](https://pro.arcgis.com/en/pro-app/help/analysis/geoprocessing/modelbuilder/what-is-modelbuilder-.htm).

## What is Model Builder?
 Model Builder is a visual programming workflow within ESRI Products that can utilize everything within ArcPro to help create new tools that combine and utilize those assets. 
 
 ## Using Model Builder
  Model Builder is located in the Analysis ribbon, this will create a new blank window that is the workspace for Model Builder.
  
  ![image](https://user-images.githubusercontent.com/60631222/76147496-cb30e300-606a-11ea-97cf-f7ff89c21fd7.png)

### Model Builder Ribbon

Some useful new tools appear in the new Model Builder ribbon that appears. 

![image](https://user-images.githubusercontent.com/60631222/76253875-d9752f80-6221-11ea-84b9-a3374be59f87.png)

A majority of the icons in this ribbon are unique to Model Builder, but are fairly straightforward.

The main section in this ribbon is the Insert section. This is where you get a majority of the variables and tools to create your model.

The Tool icon is a search browser of all the tools in ArcPro that can be adde into this workspace.
![image](https://user-images.githubusercontent.com/60631222/76255007-cf543080-6223-11ea-87c5-72cac9c7b7e6.png)

The Variable icon allows you to create an empty bubble that can be defined as any specific [data type](https://pro.arcgis.com/en/pro-app/help/analysis/geoprocessing/modelbuilder/modelbuilder-vocabulary.htm). This can be a number of different things, but are usually raster or vector data. This icon is more useful if you want variables that are unusual in nature, as you can create variables through the tool function.

![image](https://user-images.githubusercontent.com/60631222/76255633-e21b3500-6224-11ea-93b0-ad6ceda21f8e.png)

Iterators are more for advanced Model Builder techniques and will not fully be covered here, but they are tools that allow one to repeat processes on data sets.

![image](https://user-images.githubusercontent.com/60631222/76256125-c6645e80-6225-11ea-86c9-ea91bc58c19c.png)

Utilities are other advanced techniques in Model Building that focus on the basic math and adding more python expressions to the model.

![image](https://user-images.githubusercontent.com/60631222/76256831-f6f8c800-6226-11ea-91c4-63d572b84de4.png)

The Logical icon focuses on creating and merging if-then statements, it offers several if-then statements for you to use.

![image](https://user-images.githubusercontent.com/60631222/76257123-75ee0080-6227-11ea-84a3-e6e378f7b843.png)

The Labeling icon creates a text box that can be edited like other textboxes.

### Creating A Model

The first step to any project is to plan out what you want the tool or model to be. This is even more important when talking about Model Builder as this is how you will build this model and connect the tools together.

There are 3 basic elements that constitute a model.



