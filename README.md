# snONP
Backcountry drinking water monitoring for Olympic National Park

**Project Title:** snONP

**Team Members:** Olivia Carroll, Owen Nevaril

**Project Summary:** We will be investigating changes in snow cover in proximity to backcountry trails in Olympic National Park during the summer season, as snow can provide a vital drinking water resource when streamflows are minimal. We will be looking at how the snow cover patterns change over time and what the implications are for backcountry recreation in areas with water scarcity. We will also investigate the influence of the extent of the snow pack on these streamflows, as snow has downstream effects on drinking water supply for local residents.

**Objective:** Determine availability of snow as a drinking water resource for backcountry recreators in Olympic National Park and snow effects on downstream drinking water use. Relate snow pack to streamflows to determine periods when snow is a critical resource and its impact on downstream flows.

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
- Open Street Maps was used to determine trail locations and Olympic National Park boundaries.
- The Nationwide Rivers Inventory was used to determine river geometries within Olympic National Park.
- USGS streamflow gauge data supplied flow rates for rivers of interest on the Olympic Peninsula. Station locations were also supplied by the USGS.
- Watershed boundary data was pulled from the ArcGIS Hub Map: National Watershed Boundary Dataset (WBD): Hydrologic Unit Code 10-Digit Basins of Washington State.
- SENTINEL-2 was used to obtain reflectance data to determine snow cover. We investigated LANDSAT-8 to determine snow extent using NDSI, but chose to go with SENTINEL-2 data. 

**Tools/Packages Used:** Geopandas, rasterio, rioxarray, numpy, pandas, matplotlib, pyproj, osmnx, contextily, dataretrieval.nwis, requests, easysnowdata, shapely, pystac_client, planetary computer, odc.stac, datetime

**Planned Approach:** (From the beginning of the quarter) We will be looking at streamflow gauge time series from USGS to identify periods where snow will be the primary water resource. For those identified periods, we will use snow cover data from one of the potential satellite sources listed above to determine snow cover extent in areas surrounding key trails and streams in Olympic National Park. We will compare the extent of snow cover to downstream flows to determine the relationship between these two variables. We will look for trends in that relationship so that we can come to a conclusion on how they are related. To investigate snow as a potential drinking water resource, we will look at those periods where snow is the primary water resource and see if there is enough snow to support recreation activity. We may use trail report images or images from the National Park Service to look at snow quality, just from a simple visual inspection, to see if it should be consumed (TBD).

**Updated Approach:** (From the end of the quarter) First, we used USGS streamflow gauge time series for the rivers in Olympic National Park to identify high, medium, and low flow water years. For these water years, we determined a month range during the summer that had adequate Sentinel-2 reflectivity data with minimal cloud cover. We took the median of these images and calculated the NDSI for these periods. We pulled relevant features and their geometries into our notebooks for analysis; these features included rivers, trails, watershed boundaries, usgs stations, the ONP boundary, and glacial extents. We then calculated snow area by applying an NDSI mask and multiplying the number of snow identified pixels by the area of the pixel. This snow area extent calculation was determined for several watersheds, the park as a whole, and within a buffer of the trail system. We equate snow extent within the trail buffer to its availability as a drinking water resource to backcountry recreators. We correlated streamflows and snow extent within watersheds to comment on snow impact on downstream drinking water resources.

**Expected Outcomes:** There will be less drinking water resources available during summer months and over years with drought conditions. We expect that a high snow pack will be correlated to higher streamflows. 

**Results of Analysis:** 

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


**References:** 
Presentation specific references are included in the reference slide of our presentation pdf.

Data and coding example references are shown here:
**ADD REFERENCES HERE**

Included some links in our dataset section, more references to come as we work on our project.
Snow cover examples to reference:  https://nbviewer.org/github/egagli/easysnowdata/blob/main/docs/examples/remote_sensing_examples.ipynb
Trail Vector Data (openstreetmap and osmnx):  https://github.com/gboeing/osmnx
USGS Gauges: https://waterdata.usgs.gov/state/washington/ 
(Coding Examples): https://github.com/SnowEx/spicy-snow/blob/main/notebooks/tutorial/04analysis.ipynb



