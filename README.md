Mapping Trail Ownership in San Diego County
This project creates an interactive GIS tool that shows which agencies manage hiking trail segments across San Diego County. Trail data from OpenStreetMap is spatially joined with land ownership data to reveal how trails cross federal, state, local, and non-profit lands.
Objective
The goal of this project is to provide an easy-to-use way to visualize trail ownership and management responsibility. Trails often feel seamless to users, but management can change multiple times along a single route. This project makes those boundaries visible.
Data Sources
⦁	San Diego County Boundary (San Diego County GIS)
⦁	California Land Ownership Dataset (California State Geoportal)
⦁	Trail data from OpenStreetMap accessed using OSMnx
Raw datasets are not included due to size and licensing considerations.
Methods
⦁	Reprojected all data to WGS84 (EPSG:4326) for compatibility with OpenStreetMap and Folium
⦁	Clipped statewide land ownership data to San Diego County
⦁	Retrieved trail data from OpenStreetMap using a tiled grid approach to avoid query limits
⦁	Converted OSM network data to line features
⦁	Spatially joined trail segments with land ownership polygons
⦁	Classified trails by ownership level, group, and agency
⦁	Visualized results using static maps and an interactive Folium web map
Tools & Libraries
Python, GeoPandas, OSMnx, Folium, Shapely, Pandas, NumPy, Matplotlib
Outputs
⦁	Interactive web map showing trail ownership by agency
⦁	Static maps of land ownership patterns
⦁	Exported trail shapefile for reuse
Why This Matters
Understanding who manages trail systems is important for recreation planning, land stewardship, and transparency. This project highlights the shared responsibility involved in maintaining public trail networks.
