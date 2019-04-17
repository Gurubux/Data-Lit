Install OpenFire a Data Cleaning tool - http://openrefine.org/
Import the following data in OpenFire application on the browser http://data.freeyourmetadata.org/powerhouse-museum/

Facets - Text Facet and Numeric Facets

----Steps-----
1. REMOVE BLANK
Record Id column - Facet -> Numeric
Record Id column - Edit Cell -> Common Transformation -> To number
2 Non-numeric rows
All Column - Edit Rows -> Remove all matching Column

2. Remove Duplicates
Record Id Column - Sort ->numbers-Smallest First [Re-order Rows Permanently]


Summary
Facets - Divide your data into buckets to make it easier to look at
Atomization - Breaking a multi-valued cell into multiple cells
Clustering - A technique to remove inconsistencies from labels
Blank Down - Remove duplicate records in OpenRefine (Don't forget to permanently sort the rows first. Then "blank down" and delete all matching.)