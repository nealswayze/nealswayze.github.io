---
title: "GEDI Project - First Update"
layout: post
---

At the Vogeler lab, we are all about exploring new ways to leverage, model, and visualize remote sensing data. 

The NASA Global Ecosystem Dynamics Investigation (aka GEDI) is a recent NASA project using high resolution laser ranging observations to model the three dimensional structure of the earth. The GEDI instrument makes precise measurements of forest canopy height, canopy vertical structure, and surface elevation.

The GEDI sensor sends out pulses of laser light, which travel from the sensor to the earths surface, interact with the ground/vegetation, then a certain proportion of the light pulse returns and is captured by the sensors telescope. The time between the emission and reception of the light pulse is then used to calculate a waveform (distribution). These waveforms are further processed to estimate an elevation, ground surface, and a variety of canopy metrics, including relative height, percent cover, foilage height diversity, and plant area index.

Part of investigating new data comes with the task of visualizing abstract data. Sure, tables and graphs are typical, but what about something a bit more visually appealing? 

One of my recent efforts has been focused on visulazing GEDI spaceborne LiDAR data in three dimensional space. Here are the simplified steps that I use to get the data ready to visualize

- Step 1: Download the GEDI data in granules from the LPDACC

- Step 2: Read the raw GEDI .h5 files into R using the rGEDI package

- Step 3: Filter the GEDI data to the desired date range, geographic extent, and desired parameters 

    - full power beams only
    - nightime shots only
    - sensitivity > 0.95
    - quality flag = 1
    - degrade flag = 0
    
- Step 4: Once I have filtered the GEDI data and gotten it into a more familar format (dataframe) I leverage the lidR package in R to coerce the dataframe object into a .las file ( a commong point cloud format) using the geographic coordinates and desired metrics for each GEDI footprint.

- Step 5:  Once you have a .las file, easy visualization of the GEDI data in "three dimensional" space (its still on your computer screen) using a free point cloud viewing program, like CloudCompare.

Below is a visualized three dimensional example of GEDI footprint elevations across our desired study region (spanning Colorado, Wyoming, Idaho, Oregon, Washington, and Montana)

![title](https://i.imgur.com/Z6c221z.jpg)

Each point in this image is a GEDI waveform footprint, scaled on the Z axis as elevation. 


