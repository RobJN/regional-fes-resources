Started with file 'Cleaned100_a_dGSP.geojson' from 'GSPs 2019' folder as this was the last version on the original data projection (EPSG:27700 OS National Grid Eastings/Northing) before low quality transformation to latitude/longitude.

Apply the same python script changes as last year to create 'GSP_2021_v1.geojson'. This is to adjust for GSPs we don't have mapped (e.g. embeeded offshore wind OFTOs).

## ENW changes
The steps here use ENW data to split the merged GSP area "Harker/Hutton" (HARK_1;HUTT_1;RRIG). The ENW data was sourced from their heat map tool at https://www.enwl.co.uk/get-connected/network-information/heatmap-tool/

Steps were:
1. Download the data from ENW webiste (ENWL Heatmap Tool.kmz)
2. Open in QGIS and save the Primary layer as a Primary_27700.CSV retaining following columns: name, Easting, Northing, Type, Voltage__kV_BSP_Group, BCA_Group__GSP_
3. Open the resultant CSV in QGIS using Geometry CRS=ESPG:27700, X-field=Easting, Y-field=Northing
4. Created Veronoi polygons of the CSV point data and then disolved by GSP.
5. From here we can manipulate the data to extract a line that is the dividing line between Primary substations associated with Harker GSP and Primary substations associated with Hutton GSP as shown in the image below,
6. Use QGIS process tool "Split with Line" to subdivide the two GSPs and save the final result as 'GSP_2021_v2.geojson'.
