# Connecticut Census Tract -> Zip Code Crosswalk

The `data/tract2zip.csv` file contains a crosswalk between CT census tracts (as defined by 2010 US Census) and towns in CT. **Note that some tracts cross zip boundaries, therefore this crosswalk is approximate**. This crosswalk contains 829 tracts that are matched to 282 zip codes.

```
tract_fips,tract_name,tract_name_full,zipcode
"09003405700","4057",Census Tract 4057,"06010"
"09003510200","5102",Census Tract 5102,"06108"
"09003510400","5104",Census Tract 5104,"06108"
"09015901100","9011",Census Tract 9011,"06281"
"09003510300","5103",Census Tract 5103,"06108"
```

To prevent Excel from transforming FIPS codes and zip codes to numbers automatically (which leads to missing leading 0s), do the following:

1. Open Excel, New workbook
1. Go to File > Import > CSV file
1. Choose file, and select "text" as type of `tract_fips` and `zipcode` columns


### How it was generated
In QGIS, open census tract boundaries, calculate their centroids, and perform nearest neighbor spatial join (NNJoin plugin) to assign the nearest zipcode. Most centroids fall within town boundaries directly, and centroids
of some coastal tracts are slightly off the nearest town.

### Source datasets

* Connecticut zipcode boundaries: https://data.ct.gov/Government/Zip-Code-Tabulation-Area-Boundaries/n7kw-xx5z
* Connecticut census tract boundaries: https://www.census.gov/cgi-bin/geo/shapefiles/index.php?year=2019&layergroup=Census+Tracts

### License

Released under MIT license. Feel free to use for all sorts of projects. We will appreciate if you credited CTData Collaborative, although this is not required.
