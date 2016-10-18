### Project Title: Data exploration using GRACE-derived groundwater levels and well point datasets


#### The problem

Tools are needed to connect remote sensing data that varies in space and time to point measurements at specific locations and time intervals. Studies have analyzed operational, technical, institutional, financial, and environmental predictors of functionality for data collected from over 25,000 community-managed handpumps in Liberia, Sierra Leone, and Uganda (Foster (2013)). Lahren and Cook (2016) code and analyze the reasons for failure in 250,000 water points in 25 countries collected using the Water Point Data Exchange (WPDx). They find that 30% of boreholes are not functioning, with a further 12.5% that are functional but with qualifiers. “Technical or mechanical” reasons are most commonly cited as the reason for non-functionality (55%).  

Remote sensing data: The Gravity Recovery and Climate Experiment (GRACE:joint mission of NASA and the German Aerospace Center)  measures the Earth's gravity anomalies to study how mass is distributed around the planet and used for studying Earth's eceans, geology, and climate. 

Point data: The Water Point Data Exchange WPDx) is a global platfrom for sharing water point data to understand water services with 240,000 + water points in the dataset with the quantity of data varying between government support for complete datasets (all 101,000 water points in Uganda) as well as data in other countries with known GRACE observable groundwater levels (India).  

- exploration of spatial statistics offers insights about spatial patterns, trends and spatial relationships
- explore error structure
- impact of terrain on SWE distribution

- what metric do we use to assess model quality
 
#### Application Example

Can reasons for well failure using geolocated water points be linked to falling groundwater levels using spatial correlation and spatial statistics ? 

In the mountains, snow depth variability is caused by both accumulation and ablation processes with varying effects from terrain features, wind and vegetation cover. Current estimation method of the amount of water stored in the snowpack has very poor representation of snow spatial variability as it is based on statistical methods and index forecasts using sparse point location data. Recent advancements in LiDAR technology make possible the acquisition of spatially distributed snow depth data at high resolution (1 to 3 m) over large watersheds. Understanding snow depth spatial variability and differential snow melt patterns across complex terrain is crucial for estimating total water stored in the snowpack, and to support spatially distributed forecast hydrologic models. 

<br>
<img src="img/hydroGrid.png" width = "500" border = "10">
Hydrologic model grid representation. For each model grid cell a single value is computed. Typical model scales are 30, 90, 150m and larger. Running a model at 3-m scale is not feasible due to high computational effort.

These repeat, high-resolution snow depth spatial datasets provide new opportunities to: 
1) understand model subpixel spatial variability of snow depth (see example in Figure 1) across a range of model scales as the ablation season progresses, and 
2) examine spatial patterns of snow depth as a function of terrain and vegetation features for integration with hydrologic modeling.

#### Sample data

The data provided consist of LiDAR- derived snow depth datasets over the Tuolumne River watershed, source of San Francisco water supply. The data were acquired by NASA JPL using airborne LiDAR technology as part of the Airborne Snow Observatory (ASO) program. The area is about 2709 km2. The spatial resolution of the snow depth grids is 3m, making each grid of 17699 x 16780  elements and about 1.16GB geotiffs in size. The dataset is composed of the bare earth model (digital elevation model, DEM), and snow depth spatial grids on 11 occasions in 2014.

- DEM 
- vegetation
- ASO
- precip
- WRF output

#### Existing methods

How do people generally work with these data? What are some of the drawbacks and challenges?

#### Project Ideas 

1. Identify and use spatial statistics and metrics to characterize snow depth spatial variability. Potential methods can range from moving window statistics and correlation and regression techniques, to variogram and principal component analyses. 
2. Analyze snow depth and snowmelt patterns as a function of both terrain and vegetation cover to examine the relative influence of both factors on snow depth spatial variability and melt rates (examples of terrain-derived data include elevation, curvature, slope, aspect, viewshed (for shade), and topographic radiation).

#### Potential tools:

* [scikit-learn](http://scikit-learn.org/stable/index.html)
* Earth System Modeling Framework Python interface: [ESMPy](https://www.earthsystemcog.org/projects/esmf/)

<img src = "https://github.com/geohackweek/geohackweek.github.io/blob/master/img/ndarray_icon.png" width = "60"> [xarray](https://geohackweek.github.io/nDarrays/)


#### Background reading: 

* Deems, J. S., T. H. Painter, and D. C. Finnegan. 2013. Lidar measurement of snow depth: a review. Journal of Glaciology 59(215): 467-479, doi:10.3189/2013JoG12J154.
* López-Moreno, J. I., Revuelto J., Fassnacht S. R., Azorín-Molina C., Vicente-Serrano S. M., Morán-Tejeda E., and Sexstone G. A. (2015), Snowpack variability across various spatio-temporal resolutions, Hydrol. Process., 29, 1213–1224, doi:10.1002/hyp10245
* Fassnacht, S. R., and J. S. Deems. 2006. Measurement Sampling and Scaling for Deep Montane Snow Depth Data. Hydrological Processes 20: 829-838, doi:10.1002/hyp.6119.
* Revuelto, J.J. I. López-Moreno,C. Azorin-Molina, and S. M. Vicente-Serrano (2015),Canopy influence on snow depth distribution in a pine stand determined from terrestrial laser data,Water Resour. Res., 51, 3476–3489, doi:10.1002/2014WR016496.
* Revuelto, J., J. I. Lopez-Moreno, C. Azorin-Molina, and S. M. Vicente-Serrano (2014), Topographic control of snowpack distribution in a small catchment in the central Spanish Pyrenees: Intra- and inter-annual persistence, Cryosphere, 8, 1989–2006, doi:10.5194/tc-8-1989-2014.

