# R spatial workflow roadmap
Tim Appelhans, ...  
November 23, 2016  



## Introduction

The document is organised according to the minimum main steps involved in spatial workflow. Please contribute by expanding this document in any way you see fit but try to be as concise and clear as possible. **If you have extended input to any of the major points, please provide a stand-alone document (rmd & html) and include a link to it in the main document at the relevant position.** Questions regrding unclear points should probably be made as an iussue referencing the main document.

To visualise the general idea of spatial workflow I have simplified the 'tidyverse' workflow model and added main packages involved in the individual steps.

![](./images/minimum_workflow.svg)

Please note that this is far from complete so feel free to manipulate and adjust this svg file as you see fit...

## Import


## Manipulate

### Projections
 * [dggridR](https://cran.r-project.org/web/packages/dggridR/index.html). **Inputs:** lat/lon pairs and a package-specific discrete grid definition. **Outputs:** Discrete grid cell numbers, data frames suitable for plotting cells as polygons in ggplot2.
 
### Terrain Analysis
 * rgrass7
 * spgrass6
 * rqgis

## Visualise
In this context visualise refers to quick visual inspection of data during workflow. For final presentation grade visualisations refer to section *Communicate*

This is what e.g. packages **mapview** and **quickmapr** are written for (the latter can now be used within mapview by setting `mapviewOptions(platform = "quickmapr")`. Package **tmap** has function `qtm()` for quick plotting/viewing.

### mapview
**mapview** currently does two things, it

1. visualises the data using leaflet and stores the leaflet map in slot `@map` and 
2. stores the modifed object(s) that are visualised in a list in slot `@object` - 
the intention of this is to enable the user to track manipulations that have necessarily been carried out on the object(s) to correctly visualise it (e.g. re-projection).

A comprehensive overview of mapview functionality can be found [here](http://environmentalinformatics-marburg.github.io/mapview/introduction.html)

More thoughts on where we want to take mapview are outlined in

[chapters/visualise/mapview.html](chapters/visualise/mapview.html)

## Edit
Interactive feature manipulation is an integral part of any GIS system and provides easy and quick access to modify individual features. In many cases it makes sense to modify features programmatically for which R already provides a wealth of functionality. 

For a more detailed discussion on this please refer to

[chapters/edit/edit.html](chapters/edit/edit.html)

## Communicate
