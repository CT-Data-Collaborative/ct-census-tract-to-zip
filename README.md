# Connecticut Census Tract to Town Crosswalk

The `data/tract2town.csv` file contains a crosswalk between CT census tracts (as defined by 2010 US Census) and
towns in CT. **Note that some tracts cross town boundaries,
therefore this crosswalk is approximate**. This is usually the case for very small towns.
This crosswalk contains 829 tracts that are matched to 168 towns (*Canaan* is missing its own census tract).

|tract_fips|tract_name|town|county|town_fips
|--|--|--|--|--|
|09003405700|Census Tract 4057|Bristol|Hartford|0900308490
|09003510200|Census Tract 5102|East Hartford|Hartford|0900322630
|09003510400|Census Tract 5104|East Hartford|Hartford|0900322630
|09015901100|Census Tract 9011|Woodstock|Windham|0901588190
|09003510300|Census Tract 5103|East Hartford|Hartford|0900322630


To prevent Excel from transforming FIPS codes to numbers automatically
(which leads to missing leading 0s), do the following:

1. Open Excel, New workbook
1. Go to File > Import > CSV file
1. Choose file, and select "text" as type of tract_fips and town_fips columns


### How it was generated
In QGIS, open census tract boundaries, calculate their centroids, and perform nearest neighbor spatial join
(NNJoin plugin) to assign the nearest town. Most centroids fall within town boundaries directly, and centroids
of some coastal tracts are slightly off the nearest town.

### Source datasets

* Connecticut town boundaries: https://data.ct.gov/Government/Town-Boundary-Index-Map/evyv-fqzg
* Connecticut census tract boundaries: https://www.census.gov/cgi-bin/geo/shapefiles/index.php?year=2019&layergroup=Census+Tracts

### License

Released under MIT license. Feel free to use for all sorts of projects. We will appreciate if you credited CTData Collaborative, although this is not required.
