# Week 1 — Project Brief

## Project Title
**GIS-Based Groundwater Potential Mapping of Ago-Iwoye, Ogun State**

## Project Question
**Which areas of Ago-Iwoye have the highest potential for groundwater occurrence?**

## Why I Chose This Project

Groundwater is an important source of water for many communities, but it is not distributed equally everywhere.
I want to use GIS to look at the different environmental and geological factors around Ago-Iwoye and understand how they can help in identifying areas with greater groundwater potential.
This project will also help me improve my practical skills in QGIS, especially in data collection, coordinate systems, clipping, reprojection, raster processing and spatial analysis.

## Study Area

The study area is **Ago-Iwoye, Ogun State, Nigeria**.
The different datasets will be prepared and clipped to the study area so that the analysis focuses specifically on Ago-Iwoye.

## What I Want to Achieve
The main objectives of the project are to:

1. Collect the spatial data needed for the groundwater study.
2. Prepare the datasets so they can be used together in QGIS.
3. Examine factors such as geology, elevation, slope, drainage, soil, rainfall and land cover.
4. Derive useful information such as slope and lineaments from the available data.
5. Combine the relevant factors to support a groundwater-potential assessment of Ago-Iwoye.

# Data I Need

## 1. Study-Area Boundary
**Dataset:** Study-area boundary
**Source:** OpenStreetMap
**Link:** https://www.openstreetmap.org/export

**What I need it for:**  
To define the Ago-Iwoye area and use it to clip the other datasets.
**Format:** Vector data.
I also considered GADM for administrative boundaries.
**GADM Link:** https://gadm.org/data.html

## 2. Geology
**Dataset:** Geological data
**Source:** Nigeria Geological Survey Agency (NGSA)
**Link:** https://ngsa.gov.ng/geological-maps/

**What I need it for:**  
To understand the underlying rock types and geological conditions around Ago-Iwoye because geology can influence groundwater storage and movement.
**Format:** Geological map/GIS data depending on the available NGSA product.
**NGSA Geological Mapping Link:**  
https://ngsa.gov.ng/geological-mapping/


## 3. Elevation
**Dataset:** Copernicus DEM GLO-30
**Source:** Copernicus Data Space Ecosystem
**Link:** https://dataspace.copernicus.eu/explore-data/data-collections/copernicus-contributing-missions/collections-description/COP-DEM

**What I need it for:**  
To obtain elevation information for the study area.
**Resolution:** 30 m
**Format:** Raster
The DEM will also be used to derive slope and create terrain visualisations such as hillshade.


## 4. Slope
**Dataset:** Slope
**Source:** Derived from the Copernicus DEM in QGIS
**Source DEM Link:**  
https://dataspace.copernicus.eu/explore-data/data-collections/copernicus-contributing-missions/collections-description/COP-DEM

**What I need it for:**  
To show the steepness of the terrain and help understand factors such as surface runoff and infiltration.
**Format:** Raster
Slope will be generated in QGIS from the prepared DEM, so it does not need to be downloaded separately.


## 5. HydroSHEDS

**Dataset:** HydroSHEDS hydrological data
**Source:** HydroSHEDS
**Link:** https://www.hydrosheds.org/hydrosheds-core-downloads
**Product Information:**  
https://www.hydrosheds.org/products/hydrosheds

**What I need it for:**  
To provide hydrological information for understanding drainage and water-flow patterns.
**Format:** Raster/GeoTIFF
The data will be clipped to the Ago-Iwoye study area before analysis.

## 6. HydroRIVERS
**Dataset:** HydroRIVERS
**Source:** HydroSHEDS
**Link:** https://www.hydrosheds.org/products/hydrorivers

**What I need it for:**  
To show rivers and streams around the study area and support the drainage analysis.
**Format:** Vector/Shapefile
The Africa dataset is approximately 108 MB and will be clipped to the Ago-Iwoye study area.

## 7. Lineaments
**Dataset:** Lineaments
**Source:** Derived from DEM/hillshade analysis in QGIS
**Source DEM Link:**  
https://dataspace.copernicus.eu/explore-data/data-collections/copernicus-contributing-missions/collections-description/COP-DEM

**What I need it for:**  
To identify possible geological or structural features that may influence groundwater movement.
**Format:** Vector lines
The lineaments will be interpreted from terrain visualisations such as hillshade and stored as a separate project layer.

## 8. Soil
**Dataset:** SoilGrids
**Source:** ISRIC — World Soil Information
**Link:** https://isric.org/explore/soilgrids
**Data Access:**  
https://docs.isric.org/globaldata/soilgrids/SoilGrids_faqs_02.html
**Data Directory:**  
https://files.isric.org/soilgrids/latest/data/

**What I need it for:**  
To provide soil information that can help describe conditions affecting infiltration and the movement of water into the ground.
**Resolution:** 250 m
**Format:** Raster/GeoTIFF


## 9. Land Cover
**Dataset:** ESA WorldCover
**Source:** European Space Agency (ESA)
**Link:** https://esa-worldcover.org/en/data-access

**What I need it for:**  
To understand the surface characteristics of Ago-Iwoye, including vegetation, built-up areas, bare land and other land-cover classes.
**Resolution:** 10 m
**Format:** Raster/GeoTIFF


## 10. Rainfall
**Dataset:** CHIRPS Rainfall
**Source:** Climate Hazards Center, University of California, Santa Barbara
**Main Link:** https://www.chc.ucsb.edu/data/chirps3
**Data Download Link:**  
https://data.chc.ucsb.edu/products/CHIRPS/v3.0/

**What I need it for:**  
To provide rainfall information that can help in considering water input and potential groundwater recharge.
**Resolution:** 0.05° (approximately 5 km)
**Format:** Raster/GeoTIFF


## 11. GRID3
**Dataset:** GRID3 Nigeria Spatial Data
**Source:** GRID3
**Link:** https://grid3.org/geospatial-data-nigeria

**What I need it for:**  
To provide supporting spatial information where relevant, such as settlements, population, boundaries and infrastructure.

**Format:** Depends on the selected GRID3 dataset.

# Working CRS
For the projected GIS work, I am using:
**EPSG:32631 — WGS 84 / UTM Zone 31N**
I choose this coordinate system because it uses metres, which is more suitable for operations such as measuring distance, creating buffers and calculating areas.

# Expected Outcome
At the end of the project, I expect to have a set of prepared spatial layers that can be analysed together to identify areas of Ago-Iwoye with different levels of groundwater potential.
The final result will be a groundwater-potential map showing how the different environmental and geological factors contribute to groundwater occurrence in the study area.
