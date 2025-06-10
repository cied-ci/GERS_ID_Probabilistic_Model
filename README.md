# Building Snapping Model to Improve Location Accuracy of Places in Overture Maps Data
This project aims to enhance the location accuracy of Overture Places by snapping them to their nearest buildings. The snapping process helps correct misplacements, such as POIs located in parking lots or those in the middle of the street.

Another goal of this project is to be able to predict when a building snap would imrpove a POI's accuracy, an when it wouldn't. This "Selective Snapping" algorithm aims to avoid snapping in certain scenarios, such as for parks, lakes, and beaches.

To better quantify the effectiveness of this algorithm, the repo matches data with OpenStreetMap for ground truth, to quantify improvement.

Steps to Run Repo:
Prerequisites: Download the OpenStreetMap parquet file for Northern California and place in same directory as other files: https://download.geofabrik.de/north-america/us/california/norcal-latest.osm.pbf

1. Closest_Building.ipynb: This notebook will take a set of Overture Places and snap them to the closest buildings. Outputs a .csv and .parquet file with the results. Note: Execution of this notebook may take over an hour depending on amount of data selected.
2. Merge_Datasets.ipynb: This notebook will read the parquet file from the previous step and merge the datapoints with the OpenStreetMap places. This step will also output new .csv and .parquet files.
3. Logistic_Regression.ipynb: This notebook trains a Logistic Regression model to predict if it makes sense to snap a place to its nearest building. Input features include the category of the place, roads (and their types) that would be crossed if the place was snapped, and the distance between the origianl location and the snapped point.
4. Data_Insights.ipynb: Using the merged parquet file containing Overture and OpenStreetMap data, will give insights about the accuracy of the algorithm, using different metrics. Will provide numbers for the algorithm that snaps everything, and for the algorithm that snaps places of specific categories.
