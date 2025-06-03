# Probabilistic Model to Improve Location Accuracy of Places in Overture Maps Data
This project focuses on calculating a confidence metric or probabilistic distribution for the most likely locations of a place in Overture's Maps Data. The goal is to use these metrics to increase location accuracy of POIs.


Steps to Run Repo:
Prerequisites: Download the OpenStreetMap parquet file for Northern California and place in same directory as other files: https://download.geofabrik.de/north-america/us/california/norcal-latest.osm.pbf

1. Closest_Building.ipynb: This notebook will take a set of Overture Places and snap them to the closest buildings. Outputs a csv and parquet file with the results. Note: Execution of this notebook may take over an hour depending on amount of data selected.
2. Merge_Datasets.ipynb: This notebook will read the parquet file from the previous step and merge the datapoints with the OpenStreetMap places.
3. Data_Insights.ipynb: Using the merged parquet file, will give insights about the accuracy of the algorithm.
