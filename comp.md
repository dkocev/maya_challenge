---
layout: post
title: Competition Details
permalink: /comp/
---

## Competition task

The goal of the challenge is to locate ancient Maya architectures (buildings, aguadas and platforms) by performing integrated image segmentation of different types of satellite imagery (from Sentinel-1 and Sentinel-2) data and aerial laser scanning data (lidar data). 

## [Comeptition platform](https://competitions.codalab.org/competitions/30429)

## Data description
The main study area is a region around Chactún, Mexico - one of the largest known Maya urban centers located in the central lowlands of the Yucatan peninsula. The area is characterized by low hills with constructions and surrounding seasonal wetlands (bajos). Chactún is located in the northern sector of the depopulated Calakmul Biosphere Reserve in Campeche, Mexico, and is completely covered by tropical semi-deciduous forest. Its urban core, composed of three concentrations of monumental architecture, has a number of plazas surrounded by temple pyramids, massive palace-like buildings, and two ball-courts. A large rectangular water reservoir lies immediately to the west of the main groups of structures. Ceramics collected from the ground surface, the architectural characteristics, and dated monuments, indicate that the center started to thrive in the Preclassic period, reaching its climax during the Late Classic (cca. A.D. 600–1000), and had an important role in the regional political hierarchy.

## Get the data
Due to storage constraints we will provide to the input data to all cometitors, seprately. Please fill-in [this form](https://forms.gle/pycuAiAZoCkrgsyg8) and we will send you the neceserary details for obtaining the data.

### Dataset example
The data considers the main area in the period 2017-2020, consisting of of Sentinel 1, Sentinel 2 and ALS (lidar) data. The entire area of interest is split into tiles, with each tile measuring 240 x 240 meters with spatial resolution of 10 meters for Sentinel data and 0.5 meters for ALS data. The Sentinel-1 and Sentinel-2 data for each tile is stored separately in multi-band TIFF files.

Sentinel-1 dataset: Level-1 Ground Range Detected (GRD) products of IW acquisition mode were acquired, for ascending and descending orbit, with two polarizations (VV and VH), and Sigma0 as backscatter coefficient. Values of backscatter coefficient were converted to decibels (dB), fitted to [-30, 5] dB interval and normalized. Then, multiple temporal statistics were calculated for each tile: mean, median, standard deviation, coefficient of variance, 5th, and 95th percentile, pixel-wise for each year separately (2017, 2018, 2019, 2020) and for the whole period (2017-2020). Each TIFF file consists of a total of 120 bands of Sentinel-1 data.

Sentinel-2 dataset: Level-2A products were acquired with reflectance data from 12 spectral bands (B01, B02, B03, B04, B05, B06, B07, B08, B8A, B09, B11, B12). All bands were resampled to 10 meter resolution. Due to geographical and climate characteristics of the test area in Chactun (often small convective clouds or haze), and characteristics of Sentinel-2 satellites (images are impeded by cloud cover), cloud mask was calculated for each acquisition date. Additionally, acquisition dates with cloud cover above 5% were excluded. Finally, we were left with 17 acquisition dates with 12 spectral bands and cloud masks for each date. In total, each TIFF file consists of 221 bands.

Additional information regarding the data structure of the Sentinel images is given in this [document](https://biasvariancelabs.github.io/maya_challenge/res/S1%20and%20S2%20TIFF%20file%20structure.pdf)

ALS (lidar) dataset: ALS data is provided both in the form of high-quality digital elevation model (DEM) with a 0.5 m spatial resolution, and an ALS visualization composite consisting of slope, sky-view factor and positive openness in separate bands. As the entire area of interest is split into tiles that coincide with Sentinel tiles measuring 240 x 240 meters, ALS derived tiles measure 480 x 480 pixels both for DEM data and visualization composites, in TIFF files.

The output of the models will be prediction of the segmentation masks for each tile in the test set. In particular, for each tile, one has three masks, one for each of the classes of man-made structures – buildings, platforms, and aguadas. These are all binary masks, where black pixels depict the presence of a structure of the selected class, and white pixels correspond to absence of any structures of that class, at some position. 

