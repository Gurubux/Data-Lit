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
Record Id Column - Sort -> Numbers-Smallest First [Re-order Rows Permanently]
Record Id Column - Blank Down
Record Id Column - Facet -> Customized Facet -> Facet by Blank
Select True - Remove all

3. Atomization
Categories Column - Edit Cells -> Split-Multivalue-Cells

4. Clustering
Allows you to automatically find similar items and combine them
For example : 
Method 			: Key Collision/Nearest Neighbour
Keying Function : Fingerprint/n-gram Fingerprint/metaphone3/colone-phonetic

Cluster Size|	Row Count|	Values in Cluster			  |	Merge?|	New Cell Value
------------|------------|--------------------------------|-------|------------------
2			|	467		 |	Musical Instruments(466 rows) |		  | Musical Instruments
			|			 |	Musical instruments(1 rows)   |       |
			|			 | 								  |	      |
2			|	151		 |	Chemical Samples(145 rows)	  |		  |	Chemical Samples
			|			 |	Chemical samples(6 rows)	  |	      |

Merge-Selected and recluster

5. Custom text transform
value.split('|').uniques().join('|')

6. Export file as tsv

Summary
Facets - Divide your data into buckets to make it easier to look at
Atomization - Breaking a multi-valued cell into multiple cells
Clustering - A technique to remove inconsistencies from labels
Blank Down - Remove duplicate records in OpenRefine (Don't forget to permanently sort the rows first. Then "blank down" and delete all matching.)