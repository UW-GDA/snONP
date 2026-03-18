# snONP
Snow as a source of backcountry and downstream drinking water in Olympic National Park

**Project Title:** snONP

**Team Members:** Olivia Carroll, Owen Nevaril

**Motivating Question** What are the implications of snow extent on drinking water in Olympic National Park and the surrouding area?

**Project Summary:** We sought to relate snow extent to drinking water availability through three main analyses. We first analyzed changes in snow cover patterns between the years of 2020 (moderate streamflow), 2022 (high average streamflow), and 2023 (low average streamflow) for the period of July 15th - August 15th, to better understand year-to-year dynamics in relation to summer drought conditions, and their implications on water scarcity. We then narrowed our scope to three main watersheds within the park (Hoh, Elwha, Queets) to understand how changes in snow extent between each year could potentially influence streamflow at reference USGS stations, which can be used to infer stream conditions upstream of the main channels. Lastly we investigated changes in snow cover in proximity to backcountry trails in Olympic National Park, as snow can provide a vital drinking water resource for both fauna and recreators when streamflows are minimal. 

**Objective:** Determine availability of snow as a drinking water resource for backcountry recreators in Olympic National Park. Relate snow pack to streamflows to determine periods when snow is a critical resource and its impact on downstream flows.

**Repository Folder Structure:**
- analysis_notebooks: contains key notebooks with code used in our analysis and figures used for data interpretation and presentation. All notebooks have brief descriptions at the top of the notebook.
    - data folder: contains downloaded external data that was unable to be pulled using APIs
    - watershed_and_trail_analysis.ipynb: Contains per watershed analysis of snow extent, correlation values between watershed snow extent and streamflow, and figure for snow extent within a buffered trail map.
    - streamflow_plots.ipynb: Contains data and figure used to identify water years of interest from streamflow data.
    - snotel_plotting.ipynb: Used to generate snow level statistics plot from SNOTEL station data.
    - composites_wy_snow.ipynb: Contains figures of composite imagery for our period and region of interest.
    - change_in_snow_22_23.ipynb: Contains figures showing snow extent changes between our high and low water years with considerations for glacial extent.
- cache: cache
- code_testing: contains notebooks with code trials that were copied into analysis notebooks. This folder need not be reviewed, as all relevant code is used in the notebooks in the analysis_notebooks folder

**Datasets:** 

Reflectance data from SENTINEL-2 was pulled from Microsoft Planetary Computer to determine and image snow cover extent.

Glacier outlines from the Randolph Glacier Inventory were used to isolate areas of seasonal snow which fluctuates greatly on the seasonal scale, and determines much of the melt-off water contributions.

USGS station streamflow data was used to determine our years of interest from summer streamflow values, which we then related to snow extent.

River systems geometries from the National Rivers Inventory allowed us to image running water proximity to snow extent.

OpenStreetMap trail and park maps indicated key areas for backcountry recreation their proximity to snow during the summer. 

Watershed boundary features from the WA DOE's ArcGIS database allowed us to calculate the extent of snow that contributed to streamflow within a particular watershed.

DATA SOURCES
- SENTINEL -2 Level 2A Data: https://planetarycomputer.microsoft.com/dataset/sentinel-2-l2a
- Randolph Glacier Inventory for the Western U.S. and Canada: https://daacdata.apps.nsidc.org/pub/DATASETS/nsidc0770_rgi_v7/regional_files/RGI2000-v7.0-C/
- Streamflow Gauge Data: https://waterdata.usgs.gov/state/washington/
- National Rivers Inventory River System Geometry: https://public-nps.opendata.arcgis.com/datasets/105a104d5a3043b0ba2a25e31ecf3ff1_0/explore?location=47.743154%2C-123.424931%2C10
- OpenStreetMap ONP Boundary and Trail Network Geometries: https://openstreetmap.us/
- Washington State Dept. of Ecology Watershed Boundary ArcGIS Geometry: https://hub.arcgis.com/datasets/24c59727ba614c4aabe41f168ec3f586_11/explore?location=47.837590%2C-123.471642%2C9

**Tools/Packages Used:** Geopandas, rasterio, rioxarray, numpy, pandas, matplotlib, pyproj, osmnx, contextily, dataretrieval.nwis, requests, easysnowdata, shapely, pystac_client, planetary computer, odc.stac, datetime

**Planned Approach:** We will be looking at streamflow gauge time series from USGS to identify periods where snow will be the primary water resource. For those identified periods, we will use snow cover data from one of the potential satellite sources listed above to determine snow cover extent in areas surrounding key trails and streams in Olympic National Park. We will compare the extent of snow cover to downstream flows to determine the relationship between these two variables. We will look for trends in that relationship so that we can come to a conclusion on how they are related. To investigate snow as a potential drinking water resource, we will look at those periods where snow is the primary water resource and see if there is enough snow to support recreation activity. We may use trail report images or images from the National Park Service to look at snow quality, just from a simple visual inspection, to see if it should be consumed (TBD).

**Expected Outcomes:** There will be less drinking water resources available during summer months and over years with drought conditions. We expect that a high snow pack will be correlated to higher streamflows.

**Results:** Snow extent varied the greatest outside of drawn glacier boundaries, but this did not account for the full snow extent area calculated, indicating some losses of glacier area as well between our high and low streamflow years. From 2022-2023, total snow area loss was around 56.95km2, while snow outside of glaciers contributed to 47.78km2 of the whole area. This could be overstimated glacier area loss due to pixel resolution where pixels existing on the border of glacier boundaries count as snow present pixels for both masks. 

From our watershed analysis, while it was difficult to determine direct contribution of snow melt to streamflow at the USGS stations, we were able to visualize snow extent for each year, and correlated those values to their respective streamflows. For the Hoh River, which had snow extents of 21.59km2 (2022) at its lowest and 35.37km2 (2023) at it highest, correlation with the mean flow over our period of interest was 0.9477, while in the Elwha, with its lowest snow extent at 5.24km2, and 17.9km2 at its highest, correlation was 0.9186. These suggest that the snow present during the summer season does have a significant impact on streamflows during this time, and is worth noting that where we had greater areas of snow extent in the Hoh watershed, correlation values were  slightly higher, indicating particular watershed's relationships with snow upstream snow area. 

When examing snow extent within 500m or the trail network, we found that for 2022 in July-Aug, 7.13km2 of snow existed within this buffer, indicating a chance for accessiblity, while in 2023 this was reduced to only 1.76km2, showing the impact on yearly snow extent on reasonable backcountry water availability. 

**Limitations:**
- Conclusions reached from qualitative connections
- Spurious correlation between mean annual discharge and snow extent
- Sentinel-2 image resolutions (NDSI: 20m; RGB: 30m)
- Cloud cover in Sentinel-2 imagery forced our period of interest
- Lack of widespread snow depth data
- Lack of data for snow contribution to streamflow and groundwater
- Conservative trail map buffering that didn't account for surrounding slopes

**Future Directions:**
- Expand analysis to non-park areas on the Olympic Peninsula
- Correlate snow extent contribution to streamflow without glacial influence and a longer data set
- Relate temperature trends to snowpack extent to allow for predictions of summer snow extent
- In depth analysis of snow extent in relation to trails:
    - Buffering the trails with relation slope
    - Add river proximity to trail buffer 

**References:** Includes dataset formatted references.
- Microsoft Planetary Computer. Planetary Computer. (n.d.). https://planetarycomputer.microsoft.com/dataset/sentinel-2-l2a 
- RGI 7.0 Consortium, 2023. Randolph Glacier Inventory - A Dataset of Global Glacier Outlines, Version 7.0. Boulder, Colorado USA. NSIDC: National Snow and Ice Data Center. doi:10.5067/f6jmovy5navz. Online access: https://doi.org/10.5067/f6jmovy5navz
- Washington Water Conditions. Washington water conditions - USGS Water Data for the Nation. (n.d.). https://waterdata.usgs.gov/state/washington/ 
- Nationwide rivers inventory official. National Park Service. (n.d.). https://public-nps.opendata.arcgis.com/datasets/105a104d5a3043b0ba2a25e31ecf3ff1_0/explore?location=47.743154%2C-123.424931%2C10  
- OpenStreetMap US. (n.d.). https://openstreetmap.us/ 
- National Watershed Boundary Dataset (WBD): Hydrologic unit code 10-digit basins of Washington State. ArcGIS Hub. (n.d.). https://hub.arcgis.com/datasets/waecy::national-watershed-boundary-dataset-wbd-hydrologic-unit-code-10-digit-basins-of-washington-state/about 
- Gagliano, E. (2025). easysnowdata (Version v0.0.15) [Computer software]. https://github.com/egagli/easysnowdata 
