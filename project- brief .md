# My Project brief

## The Question
Which areas of Ago-Iwoye have the highest potential for groundwater occurrence?

## The data I need

- Study area boundary – [GADM](https://geodata.ucdavis.edu/gadm/gadm4.1/gpkg/gadm41_NGA.gpkg) / [GRID3](https://grid3.org/geospatial-data-nigeria) – GeoPackage/Vector – ~2.6 MB for GADM
- Geology – [NGSA](https://ngsa.gov.ng/geological-maps/) – PDF/GIS layer – Size depends on map
- Elevation – [Copernicus DEM GLO-30](https://dataspace.copernicus.eu/explore-data/data-collections/copernicus-contributing-missions/collections-description/COP-DEM) – GeoTIFF – 30 m – Tile dependent
- Slope – Derived from DEM in QGIS – GeoTIFF – Generated locally
- Drainage/flow accumulation – [HydroSHEDS](https://www.hydrosheds.org/hydrosheds-core-downloads) – GeoTIFF – ~90 m – Tile dependent
- Rivers and streams – [HydroRIVERS](https://www.hydrosheds.org/products/hydrorivers) – Shapefile – ~108 MB for Africa
- Lineaments – Derived from DEM/hillshade – Vector – Generated locally
- Soil – [SoilGrids](https://soilgrids.org/) – GeoTIFF – 250 m – Area dependent
- Land cover – [ESA WorldCover](https://esa-worldcover.org/en/data-access) – GeoTIFF – 10 m – Tile dependent
- Rainfall – [CHIRPS](https://www.chc.ucsb.edu/data/chirps) – GeoTIFF – 0.05° (~5 km) – Depends on period
- Settlement extents – [GRID3](https://grid3.org/geospatial-data-nigeria) – GeoPackage/Vector – Size depends on download
- Population – [GRID3](https://grid3.org/geospatial-data-nigeria) – Raster – 100 m – Size depends on download
- Roads – [GRID3](https://grid3.org/geospatial-data-nigeria) – Vector – Size depends on download
