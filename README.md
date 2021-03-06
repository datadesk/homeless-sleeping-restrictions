# The effect of proposed restrictions on where homeless people can sleep in Los Angeles

**By [Matt Stiles](https://twitter.com/stiles) and [Ryan Menezes](https://twitter.com/ryanvmenezes)**

**Los Angeles Times**

This repository contains the datasets and code used to examine the effects of a proposed restriction on where the homeless can sleep. [The proposal](proposal-19-0602-S1.pdf) was put forward by Councilmember Mitch O’Farrell at L.A. City Hall in August.

To perform the spatial analysis, the Times used the Python programming language and a popular open-source spatial library, GeoPandas, to plot parks, schools, day care centers and some special venues — and then to draw 500-foot buffers around them. The results were then clipped by neighborhood, and the percentage of buffered area for each neighborhood was calculated. We also took steps to estimate the population of homeless people that would be affected by the proposal: Those who, quite literally, are forced to sleep on the street at night (as opposed to those who take shelter in cars or other vehicles). The relevant Python code is detailed in three Jupyter notebooks here.

**The analysis shows that at least 26% of the city -- or about 127 of the city's 476 square miles -- would be excluded for sleeping under the proposed rules. The policy would affect 15,000 homeless Angelenos who sleep on the sidewalks at night.**

## Read more

* [Maps: Could homeless people sleep in your neighborhood if new rules pass?](https://www.latimes.com/projects/homeless-sleeping-maps/)
* [Many of L.A.’s sidewalks would be off-limits for homeless people to sleep if plan passes](https://www.latimes.com/california/story/2019-09-08/homeless-sleeping-ban-rules-los-angeles )
* [L.A. is again considering limits on where homeless people can sleep — this time by schools and parks](https://www.latimes.com/california/story/2019-08-22/homeless-sidewalk-sleeping-ban-restrictions-boise-case-shelter)

## Targeted location types

The proposal isn't yet specific, so we made some assumptions about the types of locations to include. The data for these locations come from city, county and state GIS portals, and they've been clipped to the city's boundaries before the analysis. 

**We drew 500-foot buffers around these places:** 

* All public schools (polygons from the city)
* Private schools (polygons extracted from the countywide parcel file)
* Children’s day care centers (points from the state's list and related to county parcel records)
* City, county, regional state parks (only those polygons from the county's parks spatial database that are within the city limits, excluding those categorized as transportation 'parkways', such Metro rail lines)
* Special venues (polygons extracted manually from the county's parcel file)
  * Staples Center (AIN# 5138016913)
  * Los Angeles Veterans Memorial Coliseum (5037027937)
  * Hollywood Bowl (5549009903)
  * Dodger Stadium (5415018016/5415018015)
  * Universal Studios (2424043034/2424043021)
  * El Pueblo de Los Angeles Historical Monument (5408008900)
  * Hollywood Walk of Fame (Hollywood Blvd from La Brea to Gower)

## Data sources for locations

Some of these data sets — schools, for example — represent complete lists of properties. Others, such as those collected by Los Angeles County GIS officials for homeless shelters and child care centers, are compiled from official sources for private and government-related facilities, but they are not complete lists. 

* [L.A. County parcel boundaries](https://permitting.gis.lacounty.gov/permitting/rest/services/energovDev/ViewableDev/MapServer/8)
* [L.A. County land usage codes](http://egis3.lacounty.gov/dataportal/wp-content/uploads/2009/12/usecodes-chart.pdf)
* [LAUSD school boundaries](https://maps.lacity.org/lahub/rest/services/LAUSD_Schools/MapServer/2)
* [LA city/county parks](https://egis3.lacounty.gov/dataportal/2016/10/25/department-of-parks-and-recreation-county-parks-and-open-space/)
* [LA City homeless shelters](https://public.gis.lacounty.gov/public/rest/services/LACounty_Dynamic/LMS_Data_Public/MapServer/158)
* [State database of child care centers](https://data-california.opendata.arcgis.com/datasets/CalEMA::ca-child-care-centers/data?geometry=-132.669%2C32.728%2C-106.587%2C38.956&where=COUNTY%20like%20%27%25LOS%20ANGELES%25%27)
