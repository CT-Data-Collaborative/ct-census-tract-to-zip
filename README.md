# Connecticut Census Tract -> Zip Code Crosswalk

The `data/2020tract2zip.csv` and `data/2010tract2zip.csv` file contains a crosswalk between Connecticut census tracts (for 2020 or 2010) and zip codes in CT. **Note that some tracts cross zip boundaries, therefore this crosswalk is approximate**. The 2020 crosswalk contains 879 tracts and the 2010 crosswalk contains 829 tracts.

```
tract_fips10,tract_name,tract_name_full,zipcode
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
of some coastal tracts are slightly off the nearest zipcode.

### Source datasets

* Connecticut zipcode boundaries: https://data.ct.gov/Government/Zip-Code-Tabulation-Area-Boundaries/n7kw-xx5z
* Connecticut census tract boundaries: [https://www.census.gov/cgi-bin/geo/shapefiles/index.php?year=2019&layergroup=Census+Tracts
](https://www.census.gov/cgi-bin/geo/shapefiles/index.php)
### License

Released under MIT license. Feel free to use for all sorts of projects. We will appreciate if you credited CTData Collaborative, although this is not required.
