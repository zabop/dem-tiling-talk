# DEM (Digital Elevation Model) showcase

Slovakia highest point:

![](freemapSK3D.png)

From: https://www.freemap.sk/~martin/hikingmap/#style=hiking&lat=49.16471490&lng=20.13454914&zoom=14.25&bearing=-166.45&pitch=53.57&3d=true.

Madrid airport, terrain exaggeration, with low res Mapbox DEM:

![](MadridLowResDEM.png)

High res DEM:

![](MadridHighResDEM.png)

Nice Norwegian fjord in 3D:

![](Lysebotn.png)

Colored by absolute slope:

![](roadSlope.png)

QGIS version:

![](OsloSlope0.png)
![](OsloSlope1.png)
![](OsloSlope2.png)

Potential screenshot: 3D in QGIS?

# Processing description and screenshots

Start with: FESM_1m.gpkg.
https://prd-tnm.s3.amazonaws.com/index.html?prefix=StagedProducts/Elevation/1m/FullExtentSpatialMetadata/

US is divided up to many areas, we are given the URL for each area:

![](FESM_1m.png)
![](FESM_1m_arrow.png)

For each area, we have lots of TIFFs:

![](webpageOfTiffs.png)

Many of them are oddly shaped:

![](oddlyShapedTiff0.png)
![](oddlyShapedTiff1.png)
![](oddlyShapedTiff2.png)

Some aren't:

![](squareishTiff.png)

We want to create images files from elevation covering the area of specific XYZ tiles. Such as:

![](squareishTiffWithTileBorders.png)
![](oddlyShapedTiffWithTileBorders0.png)
Note that there are TIFF sides parallel with canvas sides:
![](TiffAndTilesNotIn3857.png)
It's because project CRS is now set to the CRS of the TIFF. In exchange, webmercator tile grid is tilted.

Tile boundary visualisation is available openly: https://tilevis.fly.dev/XYZ/{z}/{x}/{y}. Visualisation of borders of single tiles: [merqantile plugin](https://plugins.qgis.org/plugins/merqantile/).
