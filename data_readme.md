# Data README: Mapping Trail Ownership in San Diego County

## Overview
This project uses publicly available geospatial datasets to analyze hiking trail ownership and management in San Diego County. The datasets were obtained from authoritative government portals and open-source platforms. Raw data files are not included in this repository due to size and licensing restrictions, but instructions for access are provided below.

---

## Data Sources

### 1. San Diego County Boundary
- **Source:** San Diego County GIS Data Portal  
- **Description:** Official county boundary shapefile used to clip statewide datasets to the San Diego County extent.  
- **Access:** Available through the [San Diego County GIS Open Data site](https://www.sandiegocounty.gov/gis.html) or ArcGIS Hub.  
- **Notes:** Provides the administrative boundary necessary for spatial filtering.

---

### 2. California Land Ownership Dataset
- **Source:** California State Geoportal  
- **Description:** Polygon dataset showing land ownership and management across California, including federal, state, local, and non-profit lands.  
- **Access:** Available via the [California Geoportal](https://gis.data.ca.gov/) under “Land Ownership” or “Public Lands.”  
- **Notes:** Clipped to San Diego County for this project. Useful for identifying which agency manages land parcels intersected by trails.

---

### 3. Trail Data (OpenStreetMap via OSMnx)
- **Source:** OpenStreetMap (retrieved using the Python library OSMnx)  
- **Description:** Trail and path network data extracted from OSM using a tiled grid query approach to avoid API limits.  
- **Access:** Data is retrieved programmatically using OSMnx functions (`graph_from_polygon`, `graph_from_bbox`, etc.). Documentation: [OSMnx GitHub](https://github.com/gboeing/osmnx).  
- **Notes:** Converted from OSM network graphs to line features for spatial analysis. Trails are classified by ownership after spatial joins with land polygons.

---

## Licensing & Use
- **San Diego County GIS Data:** Public domain, but check portal terms for attribution requirements.  
- **California Land Ownership Dataset:** Open government data; attribution to California State Geoportal recommended.  
- **OpenStreetMap Data:** Licensed under the [Open Database License (ODbL)](https://www.openstreetmap.org/copyright). Any derivative maps or datasets must credit OpenStreetMap contributors.  

---

## Processing Summary
- All datasets were reprojected to **WGS84 (EPSG:4326)** for compatibility.  
- Statewide land ownership data was clipped to the San Diego County boundary.  
- Trail data was retrieved in tiles, converted to line features, and spatially joined with ownership polygons.  
- Outputs include an interactive Folium map, static maps, and an exported shapefile of trail ownership.