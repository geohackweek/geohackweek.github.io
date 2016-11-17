## Project Title:
Automating information extraction at marine terminating glaciers

## Collaborators:
Project lead: Jessica Scheick, Amaury Dehecq

Data Science lead: David Shean

Disclosure: Certain elements and potential applications of this project were borne out of Jessica Scheick’s collaborations with Jakob Abermann and Eva Maetzler while an intern at Asiaq, Greenland Survey

## Problem statement:
Currently, a massive archive of satellite imagery exists which can provide improved temporal and spatial resolution of recent observed changes in marine terminating glacier behavior, including dynamics that directly affect mass balance (flow speed, thinning, surface melt) and terminus processes (broadly, ice-ocean interactions, including calving style and rate, influences of sea ice and mélange, and freshwater flux). Recent work has illustrated the importance of ice-ocean interactions in driving glacier dynamics, yet datasets exploring how these interactions have changed over time remains limited, in part due to the challenges associated with automated extraction of information from remotely sensed datasets in polar regions. This hack considers two approaches/hacks: 1. how can automated application of existing approaches be improved, and/or 2. what information might be gained from an entirely automated analysis of 1000s of images covering a broad range of spatial and temporal scales?

- What tools can we develop or use to automate information extraction to take advantage of satellite records, despite the challenges associated with imagery collected in polar regions (clouds, polar night, sea ice, mélange, duration of dataset, etc.)?

- What do these observations tell us about glacier behavior, including dynamic glaciological responses to oceanic forcing?

- How can this information be better incorporated into ice sheet models to improve projections of future sea level rise?

## Application example:
The approaches could ultimately be applied to any marine terminating glacier or icy marine environment (including the polar oceans, fjords, and lacustrine terminating glaciers globally). For geohackweek, it would be useful to narrow the focus to one or two specific fjords.

## Research Questions:
- What can we learn about behavior and dynamic changes at marine glacier termini from some type of automated analysis of 1000s of images collected by multiple platforms?
  - Is automation of traditional approaches to remote sensing of the cryosphere sufficient?

- How do we better automate information extraction in polar regions?
  - given the presence of sea ice, mélange, and clouds, how do we glean meaningful information from an automated analysis of a large number of scenes?
  - what limitations does this impose on our data, and how do we look beyond them?

## Data:
Any and all remotely sensed, geospatial data available for the given area of interest. Although it would be interesting to incorporate information from targeted campaigns, for an analysis of this scale it might be prudent to begin with a focus on regularly derived raster image datasets from satellite sensors (including but not limited to Landsat, MODIS, ASTER, RADARSAT, DigitalGlobe WorldView, etc.)

## Existing methods:
Traditional approaches focus on delineation and feature tracking to provide information on glacier dynamics. Methods for delineating glacier ice and icebergs often require significant operator input (or are completely manual) and/or avoid use of scenes with partial cloud cover when an entire study area is not visible.

This project seeks to improve automation of existing approaches to allow a more complete use of the satellite archive for extracting meaningful data AND/OR consider what information might be gained by automated analysis of a large number of images regardless of the limitations that generally result in significant operator input.

## Proposed methods/tools:
A number of open source tools will be used, with a focus on Google Earth Engine as a platform that does not require individual download of each image to process it. Additional tools used may include QGIS and python’s GDAL/OGR (raster and vector processing) libraries.

## References/background information:
More coming soon (especially if others are interested in pursuing some version of this project!)
