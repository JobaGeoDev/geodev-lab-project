# Week 3 — Data Preparation

## What This Week Was About

This week focused on preparing the datasets for the Ago-Iwoye groundwater-potential project in QGIS.

The main aim was to make sure that the different datasets could work together properly. This involved checking coordinate reference systems, reprojecting data, clipping datasets to the study area and preparing the Copernicus DEM for further analysis.


# 1. Setting Up the Study Area

The first step was to identify and prepare the Ago-Iwoye study area.
I used OpenStreetMap data in QGIS to help identify the location and surrounding features. I then worked on isolating the Ago-Iwoye area so that the larger datasets could be clipped to the project area.
The study-area boundary will be used as the main mask for the other datasets.

**OpenStreetMap:**  
https://www.openstreetmap.org/export


# 2. Choosing the Working CRS

The main projected coordinate reference system for the project is:

**EPSG:32631 — WGS 84 / UTM Zone 31N**

I selected this CRS because it uses metres rather than degrees.

This is more suitable for GIS operations such as:

- Measuring distances
- Calculating areas
- Creating buffers
- Clipping and processing spatial data
- Working with terrain data

Using the same projected CRS also helps the different layers line up correctly during analysis.


# 3. Preparing the Study-Area Boundary

After identifying the study area, I prepared the boundary for use in QGIS.

The boundary needs to be in the same projected CRS as the other working layers.

The general process was:

1. Add the boundary data to QGIS.
2. Check its original CRS.
3. Reproject it to EPSG:32631 where necessary.
4. Check that the boundary covers the intended Ago-Iwoye area.
5. Save the prepared boundary as a separate working layer.


# 4. Preparing the Copernicus DEM

The Copernicus DEM GLO-30 was one of the main datasets prepared during this stage.

**Source:** Copernicus Data Space Ecosystem
**Link:**  
https://dataspace.copernicus.eu/explore-data/data-collections/copernicus-contributing-missions/collections-description/COP-DEM
**Resolution:** 30 m

The DEM provides elevation information and will also be used to create other terrain-related layers.

The preparation process included:

1. Accessing the Copernicus DEM.
2. Selecting the 30 m elevation data.
3. Adding the DEM to QGIS.
4. Checking the source CRS.
5. Reprojecting the DEM where necessary.
6. Setting the appropriate target extent.
7. Clipping the DEM to the Ago-Iwoye study area.
8. Saving the processed DEM for later analysis.

The prepared DEM will be used to create the slope and terrain visualisation layers.



# 5. Reprojecting the Data

The datasets used in the project do not all come in the same coordinate reference system.
For the main GIS processing, I am using:

EPSG:32631 — WGS 84 / UTM Zone 31N

Where necessary, I reprojected the datasets so that they could be used together.

The original downloaded datasets are kept separate from the processed versions so that the original data can still be referred back to if needed.


# 6. Clipping the Datasets

Some of the datasets cover very large areas.

For example, HydroRIVERS provides river information for large regions, while datasets such as SoilGrids, WorldCover and CHIRPS cover areas much larger than Ago-Iwoye.
I therefore use the Ago-Iwoye study-area boundary to clip the datasets.

The general process is:

1. Add the original dataset to QGIS.
2. Add the prepared Ago-Iwoye boundary.
3. Use the appropriate QGIS clip tool.
4. Select the Ago-Iwoye boundary as the clipping layer.
5. Save the clipped dataset as a processed layer.

This reduces the size of the working data and keeps the analysis focused on the study area.


# 7. Creating the Slope Layer

Slope is derived from the prepared DEM rather than downloaded separately.

**Source:** Copernicus DEM GLO-30
**Link:**  
https://dataspace.copernicus.eu/explore-data/data-collections/copernicus-contributing-missions/collections-description/COP-DEM
In QGIS, the DEM can be used with the terrain analysis tools to calculate slope.
The slope layer shows the steepness of the terrain across Ago-Iwoye.
This information can help in considering:

- Surface runoff
- Water movement
- Infiltration
- Terrain characteristics

The resulting slope layer is saved as a separate raster dataset.


# 8. Preparing HydroSHEDS

**Source:** HydroSHEDS

**Link:**  
https://www.hydrosheds.org/hydrosheds-core-downloads

HydroSHEDS provides hydrological information that can help describe water-flow and drainage patterns.
The preparation process includes:

1. Downloading the relevant HydroSHEDS product.
2. Adding it to QGIS.
3. Checking its CRS and extent.
4. Reprojecting it where necessary.
5. Clipping it to the Ago-Iwoye study area.
6. Saving the processed version.

The resulting data can be used to support drainage and flow-related analysis.

---

# 9. Preparing HydroRIVERS

**Source:** HydroSHEDS

**Link:**  
https://www.hydrosheds.org/products/hydrorivers

HydroRIVERS provides information about rivers and streams.

The Africa dataset covers a much larger area than Ago-Iwoye, so I need to reduce it to the study area before using it.

The preparation involves:

1. Adding HydroRIVERS to QGIS.
2. Checking the coordinate system.
3. Reprojecting it where necessary.
4. Clipping it using the Ago-Iwoye boundary.
5. Saving the processed river layer.

The processed river layer will help show the relationship between surface drainage and the groundwater study.

---

# 10. Preparing the Geological Data

**Source:** Nigeria Geological Survey Agency (NGSA)

**Link:**  
https://ngsa.gov.ng/geological-maps/

**Geological Mapping:**  
https://ngsa.gov.ng/geological-mapping/

Geology is an important part of the groundwater study because different rock types can have different effects on groundwater storage and movement.

The NGSA geological information may be provided as a map or PDF rather than a ready-to-use GIS layer.

Where necessary, the preparation process involves:

1. Obtaining the appropriate geological map.
2. Adding the map to QGIS.
3. Georeferencing it if it is provided as an image or PDF.
4. Using the appropriate coordinate system.
5. Clipping the relevant area.
6. Digitising the geological information if necessary.
7. Saving the result as a GIS layer.

The prepared geology layer can then be compared with the other groundwater-related factors.

---

# 11. Preparing Lineaments

Lineaments are treated as a derived dataset in this project.

They can be identified from terrain information such as DEM and hillshade.

**DEM Source:** Copernicus DEM GLO-30

**Link:**  
https://dataspace.copernicus.eu/explore-data/data-collections/copernicus-contributing-missions/collections-description/COP-DEM

The general process involves:

1. Preparing the DEM.
2. Creating a hillshade in QGIS.
3. Examining different terrain directions where necessary.
4. Identifying possible linear features.
5. Digitising the interpreted features.
6. Saving them as a vector layer.

The resulting lineaments can be used to investigate possible structural controls on groundwater movement.

---

# 12. Preparing SoilGrids

**Source:** ISRIC — World Soil Information

**Link:**  
https://isric.org/explore/soilgrids

**Data:**  
https://files.isric.org/soilgrids/latest/data/

Soil information can help describe conditions that affect infiltration and water movement into the ground.

The preparation process includes:

1. Selecting the required SoilGrids property.
2. Downloading the relevant raster.
3. Adding it to QGIS.
4. Checking the CRS and resolution.
5. Clipping it to the Ago-Iwoye study area.
6. Reprojecting where necessary.
7. Saving the processed raster.

**Resolution:** 250 m

---

# 13. Preparing ESA WorldCover

**Source:** European Space Agency

**Link:**  
https://esa-worldcover.org/en/data-access

ESA WorldCover provides land-cover information at approximately 10 m resolution.

The data can show classes such as:

- Tree cover
- Shrubland
- Grassland
- Cropland
- Built-up areas
- Bare or sparse vegetation
- Water

The preparation process includes:

1. Selecting the WorldCover product covering the study area.
2. Downloading the relevant tile.
3. Adding it to QGIS.
4. Checking the CRS.
5. Clipping it to the Ago-Iwoye boundary.
6. Reprojecting if necessary.
7. Saving the processed raster.

The land-cover information can provide supporting information for the groundwater analysis.

---

# 14. Preparing CHIRPS Rainfall

**Source:** Climate Hazards Center
**Main Link:**  
https://www.chc.ucsb.edu/data/chirps3
**Data Download:**  
https://data.chc.ucsb.edu/products/CHIRPS/v3.0/

CHIRPS provides rainfall information that can be used to consider rainfall input and potential groundwater recharge.

**Resolution:** 0.05° (approximately 5 km)

The preparation process includes:

1. Selecting the appropriate rainfall period.
2. Downloading the required data.
3. Adding it to QGIS.
4. Checking the raster extent and CRS.
5. Clipping it to Ago-Iwoye.
6. Reprojecting where necessary.
7. Saving the processed rainfall layer.

I need to avoid downloading an unnecessarily large time series when only a specific period is required for the project.

---

# 15. Preparing GRID3 Data

**Source:** GRID3

**Nigeria Data:**  
https://grid3.org/geospatial-data-nigeria

**GRID3 Data Hub:**  
https://data.grid3.org/

GRID3 can provide supporting spatial information such as settlements, population, roads, boundaries and infrastructure.

Only the GRID3 datasets that are relevant to the project will be included.

The preparation process includes:

1. Selecting the required GRID3 dataset.
2. Downloading the data.
3. Adding it to QGIS.
4. Checking its CRS and extent.
5. Reprojecting where necessary.
6. Clipping it to the study area.
7. Saving the processed layer.

