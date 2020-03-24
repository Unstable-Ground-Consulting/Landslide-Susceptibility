---
layout: default
title: Code
---

### Coding Attempt

Below is the attempt at coding a tool to create a buffer and preforming a clip at the same time. It was unable to work when I was testing it due to a spacing issue that I could never figure out. The rest of the coding seems sound, but as it is my first attempt I did not expect it to be perfect.

This was created by refrencing a tool created by Tyler Davis at William and Mary in order to get the tool to work properly.

### The Buff N Clip Tool

```
#!/usr/bin/env python3
# -*- coding: utf-8 -*-
#
# lsa.pyt

import os.path

import arcpy

class Toolbox(object):
    """
    The class needed for importing as an ArcGIS toolbox.
    """
    def __init__(self):
        """Toolbox class initialization"""
        self.label = "Buff N Cut"
        self.alias = "Vector"
        self.tools = [Buff]


class Buff(object):
    """
    Name:     Buff N Cut
    Features: Creates a buffer and clips layers in one go.
    History:  VERSION 1.0
              - initial attempt at an ArcGIS Toolbox
    Ref:      https://doi.org/10.1029/2000WR900090
    """

    def __init__(self):
        """
        Name:     Buff.__init__
        Inputs:   None
        Outputs:  None
        Features: Initialize the tool
        """
        # ArcGIS Tool descriptors
        self.label = "Buffer N Cut"
        self.description = (
            "Creates a Buffer and cuts Layers in one go "
        )
        self.canRunInBackground = False

        # Check that spatial analyst tools extension is enabled
        arcpy.gp.checkOutExtension("spatial")

        # Define constants and default values used in model
        self.k_pi = 3.14159
        self.deg2rad = self.k_pi / 180.0
        self.gamma_r_nm3 = 20000.0  # unit weight of soil, N/m3
        self.gamma_w_nm3 = 10000.0  # unit weight of water, N/m3



    def execute(self, parameters, messages):
        """
        Name:     Buff.execute
        Inputs:   - list, list of ArcGIS Parameter objects (parameters)
                  - list?
        Outputs:  None.
        Features: The ArcGIS toolbox tool execute function (i.e., Run)
        """
        # Get pointers to the current project and map:
        aprx = arcpy.mp.ArcGISProject("CURRENT")
        map = aprx.activeMap

        # Get user-defined parameters by list order:
        self.origin = parameters[0].valueAsText
        self.cut1 = parameters[1].valueAsText
        self.cut2 = parameters[2].valueAsText
        self.distance = parameters[3].valueAsText
        self.outBuff = parameters[4].value
        self.outcut1 = parameters[5].valueAsText
        self.outcut2 = parameters[6].valueAsText
        # Create and initialize a step progressor to update the user
        out_steps = 6
        arcpy.SetProgressor(
            "step", "Creating Buffer...", 0, out_steps, 1
        )

        # Create Buffer
        origin = arcpy.analysis.Buffer(self.origin,self.distance)
       
	# Save Buffer
	arcpy.SetProgressorLabel("Saving Buffer...")
	arcpy.SetProgressorPosition()
        fs.save(self.outBuffer)


        # Cut first set
        arcpy.SetProgressorLabel("Cliping Layer 1...")
        arcpy.SetProgressorPosition()
        cut1 = arcpy.analysis.Clip(self.cut1, origin, self.outcut1)

	# Save Clip 1
	arcpy.SetProgressorLabel("Saving Clip...")
        arcpy.SetProgressorPosition()
        fs.save(self.outcut1)


        # Cut Second set
        arcpy.SetProgressorLabel("Cliping Layer 2...")
        arcpy.SetProgressorPosition()
        cut2 = arcpy.analysis.Clip(self.cut2, origin, self.outcut2)

	# Save Clip 2
	arcpy.SetProgressorLabel("Saving Clip(2)...")
        arcpy.SetProgressorPosition()
        fs.save(self.outcut2)
       

        arcpy.SetProgressorLabel("Complete!")
        arcpy.ResetProgressor()

        # Add raster to current map
        map.addDataFromPath(self.outBuff)
        map.addDataFromPath(self.outcut1)
        map.addDataFromPath(self.outcut2)

    def getParameterInfo(self):
        """
        Name:     Buff.getParameterInfo
        Input:    None
        Outputs:  list, list of ArcGIS Parameter objects
        Features: Defines the parameter definitions
        Ref:      https://pro.arcgis.com/en/pro-app/arcpy/
                  geoprocessing_and_python/defining-parameter-data-types-in-a-
                  python-toolbox.htm
        """
        param0 = arcpy.Parameter(
            displayName = "Point, Line, Or Polygon for Buffer",
            name = "origin",
            datatype = "GPLayer",
            parameterType = "Required",
            direction = "Input"
        )
        param1 = arcpy.Parameter(
            displayName = "Layer to cut (1)",
            name = "cut1",
            datatype = "GPLayer",
            parameterType = "Required",
            direction = "Input"
        )
        param2 = arcpy.Parameter(
            displayName = "Layer to cut (2)",
            name = "cut2",
            datatype = "GPLayer",
            parameterType = "Required",
            direction = "Input"
        )
         param3 = arcpy.Parameter(
            displayName = "Buffer miles",
            name = "distance",
            datatype = "GPDouble",
            parameterType = "Required",
            direction = "Input"
        )
        # Set default soil moisture value (m)
        param3.value = 1

        param4 = arcpy.Parameter(
            displayName = "Output buffer",
            name = "outBuff",
            datatype = "DEFile",
            parameterType = "Required",
            direction = "Output"
        )
	param5 = arcpy.Parameter(
            displayName = "Output Clip1",
            name = "outclip1",
            datatype = "DEFile",
            parameterType = "Required",
            direction = "Output"
        )
	param6 = arcpy.Parameter(
            displayName = "Output Clip2",
            name = "outclip2",
            datatype = "DEFile",
            parameterType = "Required",
            direction = "Output"
        )
        # Send ArcGIS your parameters :)
        params = [param0, param1, param2, param3, param4, param5, param6]
        return params


    def isLicensed(self):
        """Set whether tool is licensed to execute."""
        return True


    def updateParameters(self, parameters):
        """This is called whenever a parameter value is changed."""
        return


    def updateMessages(self, parameters):
        """Modify messages from internal validation for each parameter."""
        return
```
