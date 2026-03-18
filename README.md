# snONP
Snow as a source of backcountry and downstream drinking water in Olympic National Park

**Project Title:** snONP

**Team Members:** Olivia Carroll, Owen Nevaril

**Motivating Question** What are the implications of snow extent on drinking water in Olympic National Park and the surrouding area?

**Project Summary:** We sought to relate snow extent to drinking water availability through three main analyses. We first analyzed changes in snow cover patterns between the years of 2020 (moderate streamflow), 2022 (high average streamflow), and 2023 (low average streamflow) for the period of July 15th - August 15th, to better understand year-to-year dynamics in relation to summer drought conditions, and their implications on water scarcity. We then narrowed our scope to three main watersheds within the park (Hoh, Elwha, Queets) to understand how changes in snow extent between each year could potentially influence streamflow at reference USGS stations, which can be used to infer stream conditions upstream of the main channels. Lastly we investigated changes in snow cover in proximity to backcountry trails in Olympic National Park, as snow can provide a vital drinking water resource for both fauna and recreators when streamflows are minimal. 

**Objective:** Determine availability of snow as a drinking water resource for backcountry recreators in Olympic National Park. Relate snow pack to streamflows to determine periods when snow is a critical resource and its impact on downstream flows.

**Datasets:** Reflectance data from SENTINEL-2 was pulled from Microsoft Planetary Computer to determine and image snow cover extent.

Glacier outlines from the Randolph Glacier Inventory were used to isolate areas of seasonal snow which fluctuates greatly on the seasonal scale, and determines much of the melt-off water contributions.

USGS station streamflow data was used to determine our years of interest from summer streamflow values, which we then related to snow extent.

River systems geometries from the National Rivers Inventory allowed us to image running water proximity to snow extent.

OpenStreetMap trail and park maps indicated key areas for backcountry recreation their proximity to snow during the summer. 

Watershed boundary features from the WA DOE's ArcGIS database allowed us to calculate the extent of snow that contributed to streamflow within a particular watershed.

DATA SOURCES
- SENTINEL -2 Level 2A Data: https://planetarycomputer.microsoft.com/dataset/sentinel-2-l2a
- Randolph Glacier Inventory for the Western U.S. and Canada: https://daacdata.apps.nsidc.org/pub/DATASETS/nsidc0770_rgi_v7/regional_files/RGI2000-v7.0-C/
- Streamflow Gauge Data: https://waterdata.usgs.gov/state/washington/
- National Rivers Inventory River System Geometry: 
- OpenStreetMap ONP Boundary and Trail Network Geometries: 
- Washington State Dept. of Ecology Watershed Boundary ArcGIS Geometry: https://hub.arcgis.com/datasets/24c59727ba614c4aabe41f168ec3f586_11/explore?location=47.837590%2C-123.471642%2C9

**Tools/Packages Used:** Geopandas, rasterio, rioxarray, numpy, pandas, matplotlib, pyproj, osmnx, contextily, dataretrieval.nwis, requests, easysnowdata, shapely, pystac_client, planetary computer, odc.stac, datetime

**Planned Approach:** We will be looking at streamflow gauge time series from USGS to identify periods where snow will be the primary water resource. For those identified periods, we will use snow cover data from one of the potential satellite sources listed above to determine snow cover extent in areas surrounding key trails and streams in Olympic National Park. We will compare the extent of snow cover to downstream flows to determine the relationship between these two variables. We will look for trends in that relationship so that we can come to a conclusion on how they are related. To investigate snow as a potential drinking water resource, we will look at those periods where snow is the primary water resource and see if there is enough snow to support recreation activity. We may use trail report images or images from the National Park Service to look at snow quality, just from a simple visual inspection, to see if it should be consumed (TBD).

**Expected Outcomes:** There will be less drinking water resources available during summer months and over years with drought conditions. We expect that a high snow pack will be correlated to higher streamflows.

**Results** Snow extent varied the greatest outside of drawn glacier boundaries, but this did not account for the full snow extent area calculated, indicating some losses of glacier area as well between our high and low streamflow years. From 2022-2023, total snow area loss was around 56.95km2, while snow outside of glaciers contributed to 47.78km2 of the whole area. This could be overstimated glacier area loss due to pixel resolution where pixels existing on the border of glacier boundaries count as snow present pixels for both masks. 

From our watershed analysis, while it was difficult to determine direct contribution of snow melt to streamflow at the USGS stations, we were able to visualize snow extent for each year, and correlated those values to their respective streamflows. For the Hoh River, which had snow extents of 21.59km2 (2022) at its lowest and 35.37km2 (2023) at it highest, correlation with the mean flow over our period of interest was 0.9477, while in the Elwha, with its lowest snow extent at 5.24km2, and 17.9km2 at its highest, correlation was 0.9186. These suggest that the snow present during the summer season does have a significant impact on streamflows during this time, and is worth noting that where we had greater areas of snow extent in the Hoh watershed, correlation values were  slightly higher, indicating particular watershed's relationships with snow upstream snow area. 

When examing snow extent within 500m or the trail network, we found that for 2022 in July-Aug, 7.13km2 of snow existed within this buffer, indicating a chance for accessiblity, while in 2023 this was reduced to only 1.76km2, showing the impact on yearly snow extent on reasonable backcountry water availability. 

**References:** Included some links in our dataset section, more references to come as we work on our project.
Snow cover examples to reference:  https://nbviewer.org/github/egagli/easysnowdata/blob/main/docs/examples/remote_sensing_examples.ipynb
Trail Vector Data (openstreetmap and osmnx):  https://github.com/gboeing/osmnx
USGS Gauges: https://waterdata.usgs.gov/state/washington/ 
(Coding Examples): https://github.com/SnowEx/spicy-snow/blob/main/notebooks/tutorial/04analysis.ipynb
Some Options we can look at linking to glaciers across the park: 
- Elwha River at Mcdonald BR Near Port Angeles, WA - USGS-12045500
- Bogachiel River Near Forks, WA - USGS-12042800
- Hoh River at US Highway 101 Near Forks, WA - USGS-12041200
- Queets River Near Clearwater, WA - USGS-12040500
- Quinault River at Quinault Lake, WA - USGS-12039500
- NF Skokomish R BL Staircase Rpds NR Hoodsport, WA - USGS-12056500
- Duckabush River Near Brinnon, WA - USGS-12054000
- Dungeness River Near Sequim, WA - USGS-12048000
Comments: Can use the stream gauge data to identify "low flow" periods. E.g.: when flow is below some percent of the yearly average, it's low-flow. Then look for remaining snow during those periods.