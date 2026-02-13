# snONP
Backcountry drinking water monitoring for Olympic National Park

**Project Title:** snONP

**Team Members:** Olivia Carroll, Owen Nevaril

**Project Summary:** We will be investigating changes in snow cover in proximity to backcountry trails in Olympic National Park during the summer season, as snow can provide a vital drinking water resource when streamflows are minimal. We will be looking at how the snow cover patterns change over time and what the implications are for backcountry recreation in areas with water scarcity. We will also investigate the influence of the extent of the snow pack on these streamflows, as local fauna use these high mountain streams as their sole water source during the dry season.

**Objective:** Determine availability of snow as a drinking water resource for backcountry recreators in Olympic National Park. Relate snow pack to streamflows to determine periods when snow is a critical resource and its impact on downstream flows.

**Datasets:** ArcGIS trail maps will indicate key areas for backcountry recreation and we will look at snow data in close proximity to these trails. We will look into using Open Street Maps as an alternative, since it may be simpler to obtain trail locations from.

We will use reflectance data from SENTINEL-2 to determine snow cover. We may use LANDSAT-8 to determine snow extent using NDSI. If we decide that we need a higher temporal resolution and are willing to reduce our spatial resolution, we will use MODIS for our snowcover data.

- Trail and River Map: https://www.arcgis.com/apps/mapviewer/index.html?webmap=dfca225b740d4ce18228a3314d87d42a
- Additional Trail and Vegetation Map: https://www.arcgis.com/apps/mapviewer/index.html?webmap=e8b07d9cf0d04268bcdb9129cdc7e088
- Marmot Habitat Map: https://www.usgs.gov/data/olympic-marmot-marmota-olympus-molmaxconus2001v1-habitat-map
- Streamflow Gauge Data: https://waterdata.usgs.gov/state/washington/

**Tools/Packages Used:** Geopandas, rasterio, rioxarray, numpy, pandas, matplotlib, + more probably!

**Planned Approach:** We will be looking at streamflow gauge time series from USGS to identify periods where snow will be the primary water resource. For those identified periods, we will use snow cover data from one of the potential satellite sources listed above to determine snow cover extent in areas surrounding key trails and streams in Olympic National Park. We will compare the extent of snow cover to downstream flows to determine the relationship between these two variables. We will look for trends in that relationship so that we can come to a conclusion on how they are related. To investigate snow as a potential drinking water resource, we will look at those periods where snow is the primary water resource and see if there is enough snow to support recreation activity. We may use trail report images or images from the National Park Service to look at snow quality, just from a simple visual inspection, to see if it should be consumed (TBD).

**Expected Outcomes:** There will be less drinking water resources available during summer months and over years with drought conditions. We expect that a high snow pack will be correlated to higher streamflows. 

**References:** Included some links in our dataset section, more references to come as we work on our project.