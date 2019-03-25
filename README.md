# ROI-Auto
Python 3 script that generates training and validation samples (geodataframes) from a shapefile database

# 1. Introduction

Image classification is one of the most  well known and used operations in remote sensing and GIS.
To evaluate the result produced by a supervised classification algorithme; the operator needs to analyse the confusion matrix, Kappa coefficient and overall accuracy generated by using training and validation samples.

These samples are often split in two:

  * 2/3 &rarr; Training samples (used to train the model);
  * 1/3 &rarr; Validation samples (used to validate the model).

The samples need to be split in a random way as to not influence the classification's evaluation.
This why this script has been developed.

# 2. Principle

The ROI-Auto python3 script reads all of the ESRI shapefiles in a directory, and using a pseudo random number generator; it determines the polygones that are going to be used for the training and validation. Then, it puts them in separate foloders (in the same directory).
At the end of the operation, a report is generated with the IDs of the polygons chosen for training / validation.

# 3. Data preparation and structure

As of now, the script only supports ESRI shapefiles.

In theory, MultiPoints shapefiles should work, although no test were done to confirm this.

Each MultiPolygon (.shp) must represent one class and one class ONLY.
The number of MultiPolygons in the directory must match the number of classes.

# 4.  Dependencies

The script will not work without the following dependencies:

  * [Python 3](https://www.python.org/) (tested on python 3.6 and 3.7)
  * [Geopandas](http://geopandas.org/)