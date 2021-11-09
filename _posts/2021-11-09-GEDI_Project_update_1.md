---
title: "GEDI Project - First Update"
layout: post
---

## GEDI Project - Overview

At the Vogeler lab, we are all about exploring new ways to leverage, model, and visualize remote sensing data. 

The NASA Global Ecosystem Dynamics Investigation (aka GEDI) is a recent NASA project using high-resolution laser ranging observations to model the three-dimensional structure of the earth. The GEDI instrument makes precise measurements of forest canopy height, canopy vertical structure, and surface elevation.

The GEDI sensor sends out pulses of laser light, which travel from the sensor to the earth's surface, interact with the ground/vegetation, then a proportion of the light pulse returns and is captured by the sensor's telescope. The time between the emission and reception of the light pulse is then used to calculate a waveform (distribution). These waveforms are further processed to estimate an elevation, ground surface, and a variety of canopy metrics, including relative height, percent cover, foilage height diversity, and plant area index.

Part of investigating new data comes with the task of visualizing abstract data. Sure, tables and graphs are typical, but what about something a bit more visually appealing? 

## Visualizing GEDI Footprint Data

- Step 1: Download the GEDI data in granules from the LPDACC

- Step 2: Read the raw GEDI .h5 files into R using the rGEDI package

- Step 3: Filter the GEDI data to the desired date range, geographic extent, and desired parameters 

    - Full power beams only
    - Nighttime shots only
    - Sensitivity > 0.95
    - Quality flag = 1
    - Degrade flag = 0
    
- Step 4: Once I have filtered the GEDI data and gotten it into a more familiar format (data frame) I leverage the lidR package in R to coerce the data frame object into a .las file ( a common point cloud format) using the geographic coordinates and desired metrics for each GEDI footprint.

- Step 5:  Once you have a .las file, easy visualization of the GEDI data in "three-dimensional" space (it's still on your computer screen) using a free point cloud viewing program, like CloudCompare.

Below is a visualized three-dimensional example of GEDI footprint elevations across our desired study region (spanning Colorado, Wyoming, Idaho, Oregon, Washington, and Montana)

![title](https://i.imgur.com/Z6c221z.jpg)

Each point in this image is a GEDI waveform footprint, scaled on the Z axis as elevation. 

{% include embed.html url="https://vimeo.com/643992138" %}

## dotnet evergreen


```
> dotnet evergreen dotnet-tor
```

<video src= "https://player.vimeo.com/video/643992138?h=4b2f89dc24&amp;badge=0&amp;autopause=0&amp;player_id=0&amp;app_id=58479" controls="controls" style="max-width: 730px;">
</video>

<video src="https://user-images.githubusercontent.com/169707/126715420-991ad821-9ac8-4b66-b79e-e0966e0f3a89.mp4" controls="controls" style="max-width: 730px;">
</video>
