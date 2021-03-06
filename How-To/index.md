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

As it is a visual method how things appear is very important. Below are just examples about how some of the icons we discussed earlier look in Model Builder. Notice that their isn't a Utilities portion as that just looks like a regular tool.

![image](https://user-images.githubusercontent.com/60631222/76470610-f303ac00-63c6-11ea-9c1b-e5f2fa1cc8c8.png)

There are 3 basic elements that constitute a basic model. These are the Variables, Tools, and Outputs that all have a unique color to identify them. Each of these elements also come with a connector to input them into Tools, Iterators, and Logicals. These are the arrows between each shape.

Variable:

Variables are the blue circles that represent most commonly data layers, but also represent other data types.

In addition to just being layers there is also the ability to turn these variables into parameters, which allow others to insert data into your model. This creates a pseudo-tool that can be downloaded and used by others. To turn the variable into a parameter you right click on the bubble and use the parameter option on the menu.

![image](https://user-images.githubusercontent.com/60631222/76626642-e8086300-650f-11ea-8480-6c8b9b159f5e.png)

When you change the variable into a parameter a large uppercase P will appear in the upper right corner of the bubble.

![image](https://user-images.githubusercontent.com/60631222/76627230-06229300-6511-11ea-9b9a-4eed492d8ab1.png)

Tool: 

Tools act just like the base tools in ArcPro, just represented visually as a yellow rounded rectangle with all the variable inputs and outputs turned into bubbles. Unlike Variables Tools have a lot more information before its ready to run. An easy way to figure out if the tool is ready to run is the color, if it has no color then there are still variables or settings that you have to finish before it can run.

![image](https://user-images.githubusercontent.com/60631222/76627710-e344ae80-6511-11ea-8346-23b82710c494.png)
 
 To see what inputs are still needed you should open the tool. To do this just right click on the tool and select the Open option in the menu. It will pull up the tool as you would see it in the Geoprocessing plane.
 
 ![image](https://user-images.githubusercontent.com/60631222/76627978-60702380-6512-11ea-8969-d3ba177dc173.png)
 
 *NOTE:* Connectors
 
 Also important in this process is how one connects the variables to the tools, when you hover over the variable you either get the move icon, represented by four directional arrows, or the hand icon. *The Hand icon* is the one that we will need to create a connector. After seeing the hand clicking and holding will create an arrow from that original spot to your mouse. Then you will hover over the tool or bubble you want to connect you and you will recieve on option window. This will tell you where in that tool your variable will fit.

![image](https://user-images.githubusercontent.com/60631222/76627636-b85a5a80-6511-11ea-98e1-6a638df62dba.png)

Finally after connecting all the relevant information the tool will now be a yellow color and indicate that it has all the information needed to run. 

![image](https://user-images.githubusercontent.com/60631222/76628658-76caaf00-6513-11ea-9b02-c8daf07644d5.png)

Outputs:

The outputs will always be a green bubble, they are variables that do not exist yet and can be connected to other tools like variables. They act exactly the same as variables, but their naming convention is just carried over from the tool's output section. Outputs will never be found on their own as they are a product of the tool.

### Running the Tool

Now that we have create the tool we want the next step is to check it for errors and run it. This is where we will use the Run grouping on the Model Builder Ribbon.

![image](https://user-images.githubusercontent.com/60631222/76629321-7848a700-6514-11ea-8655-45534c79dca6.png)

Both of these tools will always be used to verify and run the tool. The first step is to validate the model, this is just the computer running through the whole tool checking it for any errors that wouldn't allow it to run (i.e. if the data exists, if the data is in the right place, is the data type correct for the tool, etc.). If everything is good nothing will pop up it will also not alert you when certain tools don't have enough data that is what the color change is for.

Once you have validated the model the next step is to run it. This will run the model and create the output layers in the locations specified in the tools. It will not save output layers that are put into other tools as it will assume that these layers are not the final product and are just stepping stones to other data.

After Running the model your model will look different, drop shadows are added to both the tool and the output indicating that they have been ran.

![image](https://user-images.githubusercontent.com/60631222/76630183-f6597d80-6515-11ea-8997-b6c80c295d9b.png)

And done! your model has been created and the next step is to save it using the save icon. Be aware that Models actually save to your toolbox instead of a geodatabase. Thus you could compile a toolbox with all of your favorite modele to be transferred to any computer.

![image](https://user-images.githubusercontent.com/60631222/76630410-54866080-6516-11ea-8e0f-2d6f37d2ecd1.png)

## Why Use Model Builder?

What are the benifits of the Model Builder if I can just run the tools seperately anyway? Well Model Builder is great for creating complex tasks that you want to run several times, as it automates a lot of the process through the workflow. Also it allows for easy replacement of variables if something doesn't work right. Any variable can be easily replaced at the beginning without compromising the rest of the model. Also it is sometimes easier to see the whole path laid out in a visual manner to better understand the relationships of the variables. It also saves on the amount of layers that are saved as it automatically deletes the layers that are intermediates and doesn't save them to your database.

Hopefully this was useful in creating your first model, there are a lot more things that can be done with models that I didn't cover here. Enviroments that can be set for the whole model, groupings that just make it look a little nicer and help explain what is going on, the Iterators and Logicals. There is so much more and if you are interested, again go to the ESRI website on [Model Builder](https://pro.arcgis.com/en/pro-app/help/analysis/geoprocessing/modelbuilder/what-is-modelbuilder-.htm).

Finally here is just an example of the Critical Rainfall Model in Model Builder using Goruping to better understand the parts of the equation. Due to most of the variables being parameters the model is pretty grey.

![image](https://user-images.githubusercontent.com/60631222/76631093-7af8cb80-6517-11ea-90d7-0e105ad35efe.png)
