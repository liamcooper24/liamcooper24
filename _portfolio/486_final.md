---
title: "Baltimore Canopy Cover and Median Household Income"
excerpt: "Part of UMBC GES 486 coursework<br/><img src='/images/bivariate_choropleth_small.png'>"
collection: portfolio
---

## Introduction
Trees have an important role to play in urban communities, from improving overall human health to supporting already fragile or diminished ecosystems. How does this change in poorer areas and do they lack more greenery? Is there a spatial trend between median household income and tree canopy cover? This analysis looks at 5 year estimates of the American Community Survey (2022) and the NLCD canopy cover raster of the United States (2021) to see if such a relationship exists.  
## Methodology
The Tidycensus get_acs() function was used to retrieve ACS data with census tract geographies in Baltimore. Using zonal statistics in R the mean of the canopy cover raster was added to each census tract. A combined shapefile with both variables was placed into GeoDa. A queen's contiguity weights list was created to run a univariate local Moran's I on each individual variable after running a global Moran's I. This generated both significance and  clustering maps for each variable. These results were appended to the shapefile and exported for further visual processing in R and QGIS.
## Results
The cluster maps show high value clusters in red and low value clusters in blue. Income has a high value cluster by the Inner Harbor as well as in the North. Tree canopy Cover has a much stronger clustering pattern with low value clusters in the urban core and high value clusters in the urban periphery. A bivariate choropleth map of percent tree canopy cover and median household income in US dollars shows that there is no strong overlapping trend between the two. North Baltimore is the greatest hotspot of high value clusters for both variables. 

<br/><img src='/images/mhhi_clusters_large.png'>

<br/><img src='/images/conus_clusters_large.png'>

<br/><img src='/images/bivariate_choropleth_large.png'>


