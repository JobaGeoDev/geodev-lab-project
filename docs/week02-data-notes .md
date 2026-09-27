# Week 2 — Data Notes

## What This Week Was About

This week focused on finding, checking and understanding the datasets needed for my Ago-Iwoye groundwater-potential project.
The datasets come from different sources and are available in different formats, coordinate systems and resolutions. Before using them for analysis, I needed to understand what each dataset contains, where it came from and how it will be used in the project.
The main datasets I identified are the study-area boundary, geology, elevation, slope, hydrological data, rivers, lineaments, soil, land cover, rainfall and supporting GRID3 data.


# 1. Study-Area Boundary

**Dataset:** Study-area boundary

**Source:** OpenStreetMap

**Link:**  
https://www.openstreetmap.org/export

**Alternative boundary source:** GADM

**GADM Link:**  
https://gadm.org/data.html

**What I need it for:**  
The boundary is needed to define the area of interest and clip the other datasets to Ago-Iwoye.

**Format:** Vector

**Notes:**  
I worked with OpenStreetMap data in QGIS while trying to isolate the Ago-Iwoye area. The boundary needs to be checked carefully before being used as the final study-area mask.

OpenStreetMap allows data for a selected area to be exported for use in GIS. 


# 2. Geology

**Dataset:** Geological data

**Source:** Nigeria Geological Survey Agency (NGSA)

**Main Link:**  
https://ngsa.gov.ng/geological-maps/

**Geological Mapping Link:**  
https://ngsa.gov.ng/geological-mapping/

**What I need it for:**  
Geology is one of the main factors in the project because the type and arrangement of rocks can influence groundwater storage and movement.

**Format:**  
Depending on the NGSA product, the geological information may be available as a geological map, PDF or GIS-compatible data.

**Notes:**  
The NGSA website provides geological sheet maps and state geological and mineral-resource maps, including Ogun State.

If the required geology is available as a PDF or image rather than a GIS layer, it will need to be georeferenced before being used properly in QGIS.


# 3. Elevation

**Dataset:** Copernicus DEM GLO-30
**Source:** Copernicus Data Space Ecosystem
**Link:**  
https://dataspace.copernicus.eu/explore-data/data-collections/copernicus-contributing-missions/collections-description/COP-DEM

**What I need it for:**  
The DEM provides elevation information for the Ago-Iwoye study area.
It will also be used to derive slope and create terrain visualisations such as hillshade.
**Resolution:**  
30 m

**Format:**  
Raster

**Notes:**  
I used the Copernicus DEM 30 m data for the project. Access to the 30 m product requires the appropriate Copernicus Data Space access, and the platform can otherwise default to the 90 m DEM.

---

# 4. Slope

**Dataset:** Slope
**Source:** Derived from the Copernicus DEM in QGIS
**Source DEM Link:**  
https://dataspace.copernicus.eu/explore-data/data-collections/copernicus-contributing-missions/collections-description/COP-DEM

**What I need it for:**  
Slope shows how steep the terrain is.

It can help with understanding surface runoff, infiltration and the movement of water across the landscape.

**Format:**  
Raster
**Resolution:**  
Derived from the DEM.

**Notes:**  
Slope is not a separate downloaded dataset. It will be generated in QGIS from the prepared Copernicus DEM.

# 5. HydroSHEDS

**Dataset:** HydroSHEDS hydrological data

**Source:** HydroSHEDS

**Main Link:**  
https://www.hydrosheds.org/products/hydrosheds

**Download Link:**  
https://www.hydrosheds.org/hydrosheds-core-downloads

**What I need it for:**  
HydroSHEDS provides hydrological information that can be used to understand drainage and water-flow patterns.

For this project, the relevant information includes flow direction and flow accumulation.

**Format:**  
GeoTIFF raster
**Available resolutions:**  
3 arc-seconds, 15 arc-seconds, 30 arc-seconds, 5 arc-minutes and 6 arc-minutes, depending on the product.
**Notes:**  
The HydroSHEDS core data are distributed as GeoTIFF files. The selected dataset will be clipped to the Ago-Iwoye study area before analysis.


# 6. HydroRIVERS

**Dataset:** HydroRIVERS
**Source:** HydroSHEDS
**Link:**  
https://www.hydrosheds.org/products/hydrorivers
**What I need it for:**  
HydroRIVERS provides river and stream information that can be used to understand surface drainage around Ago-Iwoye.
**Format:**  
Shapefile / vector

**Africa dataset size:**  
Approximately 108 MB for the Africa Shapefile.


# 7. Lineaments

**Dataset:** Lineaments
**Source:** Derived from DEM and hillshade analysis
**Source DEM Link:**  
https://dataspace.copernicus.eu/explore-data/data-collections/copernicus-contributing-missions/collections-description/COP-DEM

**What I need it for:**  
Lineaments can represent geological or structural features that may influence groundwater movement.

**Format:**  
Vector lines


# 8. Soil

**Dataset:** SoilGrids
**Source:** ISRIC — World Soil Information
**Main Link:**  
https://isric.org/explore/soilgrids
**Data Link:**  
https://files.isric.org/soilgrids/latest/data/

**What I need it for:**  
Soil information can help describe conditions that influence infiltration and the movement of water into the ground.

**Resolution:**  
250 m
**Format:**  
Raster / GeoTIFF

**Notes:**  
SoilGrids provides different soil properties, including clay, sand, silt, soil organic carbon and other properties.
For this project, the most relevant soil information will be selected and clipped to the Ago-Iwoye study area.



# 9. Land Cover

**Dataset:** ESA WorldCover
**Source:** European Space Agency
**Link:**  
https://esa-worldcover.org/en/data-access

**What I need it for:**  
Land cover provides information about what is covering the Earth's surface.

It can help distinguish areas such as vegetation, built-up land, bare land, cropland and water.

**Resolution:**  
Approximately 10 m
**Format:**  
Cloud-Optimized GeoTIFF

**Notes:**  
The WorldCover products are provided in a 1° × 1° grid and at approximately 10 m resolution.
For this project, the relevant tile covering Ago-Iwoye will be selected and clipped to the study area

# 10. Rainfall

**Dataset:** CHIRPS rainfall
**Source:** Climate Hazards Center, University of California, Santa Barbara
**Main Link:**  
https://www.chc.ucsb.edu/data/chirps3
**Data Download Link:**  
https://data.chc.ucsb.edu/products/CHIRPS/v3.0/

**What I need it for:**  
Rainfall provides information about water entering the study area.

It can therefore be useful when considering potential groundwater recharge.
**Resolution:**  
0.05° (approximately 5 km)
**Format:**  
Raster

# 11. GRID3

**Dataset:** GRID3 Nigeria spatial data
**Source:** GRID3
**Nigeria Data Link:**  
https://grid3.org/geospatial-data-nigeria
**GRID3 Data Hub:**  
https://data.grid3.org/
**Nigeria Data Search:**  
https://data.grid3.org/search?tags=NGA%2CNigeria

**What I need it for:**  
GRID3 can provide supporting spatial information for the project.

Possible useful layers include:

- Administrative boundaries
- Settlements
- Population estimates
- Roads
- Health facilities
- Other supporting infrastructure

Format:
Depends on the selected dataset.

# General Data Notes

One of the main things I noticed during this stage is that the datasets come from different organisations and are provided in different formats and resolutions.
This means they cannot simply be added to QGIS and analysed immediately.

Before analysis, I need to:

- Check the coordinate reference system of each dataset.
- Reproject layers where necessary.
- Clip large datasets to the Ago-Iwoye study area.
- Check raster resolution and extent.
- Check that vector and raster layers line up correctly.
- Save cleaned versions separately from the original data.
- Keep a record of where each dataset came from.

The main working CRS for the project is:

EPSG:32631 — WGS 84 / UTM Zone 31N
The next stage is to continue preparing these datasets in QGIS so that they can be used together for the groundwater-potential analysis.
