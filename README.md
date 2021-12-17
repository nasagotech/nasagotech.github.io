# Project GOTECH: Predicting Coral Presence Using Satellite-Based LiDAR

## Josh Mattingly, Tina Guo, and Dan Schauder

A Practicum Project for the Master of Science, Analytics Program at the Georgia Institute of Technology


<img src="nasa-logo-web-rgb.png" alt="NASA" width="250"/>    <img src="CV_Logo_Primary_White.svg" alt="Coral Vita" width="150"/>    <img src="GeorgiaTech_RGB.png" alt="Georgia Tech" width="300"/>

## Background
#### Problem Statement
* While approximately 30% of the world’s marine species depend on coral reefs, “all the coral reefs in the world could be gone by 2070 if global heating continues on its current path” (Morrison et al, 2019).

* Comprehensive and accurate coral vitality data are needed for effective preservation and restoration of coral reefs, but existing datasets are fragmented, limited in scope, and rely on costly collection methods.

#### Project Aims
The Geophysical Observations Toolkit for Evaluating Coral Health (GOTECH) project was a semester-long Practicum project sponsored by NASA and Coral Vita and undertaken by Master's students at Georgia Tech in the Fall of 2021 wih the following goals:

* Establish a baseline dataset of coral health by fusing disparate open-source datasets.
* Merge baseline coral health data with data from a Lidar Sensor aboard nasa’s cloud-aerosol Lidar and infrared pathfinder satellite Observation (CALIPSO) satellite.
* Correlate Lidar Backscatter with Coral Presence.
* Interpret Trends in a Known Global Region based on Backscatter Alone.

After researching multiple potential research locations, we chose the Florida coast as our primary focus. 
<img src="Reef_Locations.png" alt="Potential Reef Locations" width="900"/>

## Methods

#### Data Fusion
A nearest neighbor approach was used to pair response variables (coral/algae for Allen Coral Atlas and coral-only for AIMS survey) with either the CALIPSO or NEO predictor datasets.

A 0.5 degree threshold was established to limit matching of CALIPSO backscatter to the response sets.

<img src="Data_Fusion.png" alt="Data Fusion Methodology" width="900"/>

A model competition framework was created, allowing fusion methodologies to be tested against a standardized set of classification models.

<img src="Dataset_Summary.png" alt="Data Fusion Methodology" width="900"/>

## Model Results
Model performance was based on the underlying dataset. Accuracy scores shown below.
<img src="accuracies.png" alt="Model Accuracy Grid" width="600"/>

<img src="accuracy_map.png" alt="Example model accuracy map" width="800"/>

###### Visualization of the un-tuned ANN on the Florida (CALIPSO + Allen Coral Atlas) dataset. Green indicates correct predictions, with red being incorrect.

## Conclusions
* Satellite-based LiDAR is a promising avenue for remote detection of coastal coral
* Most influential datapoints for prediction taken from atmospheric readings well above ocean surface
* Groundtruth data at higher spatiotemporal resolutions may be required to further improve predictive model performance

## Future Work
* Tune models for improved performance
* Fuse additional data sources (NEO, GALILEO, etc)
* Find sources where CALIPSO/LiDAR improves accuracy
* Optimize distance threshold and backscatter feature selection
* Update Distance and shape to match CALIPSO scan pattern
* Manta Tow Survey time series regression (predict amount of live coral)
* Re-run experiment with other forms of lidar (plane/ship/drone-mounted) and other research locations

## References
#### Data Sources
CALIPSO data was obtained from the NASA Langley Research Center Atmospheric Science Data Center from  https://subset.larc.nasa.gov/calipso/.

Australian Institute of Marine Science (AIMS). (2015). AIMS Long-term Monitoring Program: Crown-of-thorns starfish and benthos Manta Tow Data (Great Barrier Reef), https://doi.org/10.25845/5c09b0abf315a, accessed 10-Nov-2021.

Chlorophyll Concentration: 8-DAY AQUA/MODIS. (2018-2020). Retrieved Oct 25, 2021, from https://neo.gsfc.nasa.gov/view.php?datasetId=MY1DMW_CHLORA

Allen Coral Atlas maps, bathymetry and map statistics are © 2018-2021 Allen Coral Atlas Partnership and Vulcan, Inc. and licensed CC BY 4.0 (https://creativecommons.org/licenses/by/4.0/)

NASA Framework for the Ethical Use of Artificial Intelligence (AI). https://libguides.umgc.edu/c.php?g=1003870&p=7270670 

## Acknowledgements
This research was supported in part through research cyberinfrastructure resources and services provided by the Partnership for an Advanced Computing Environment (PACE) at the Georgia Institute of Technology, Atlanta, Georgia, USA.

Our deep thanks to the following individuals for their mentorship and gracious support of this effort:
* Dr. Newton Campbell (NASA)
* Doug Trent (NASA)
* Dr. Katey Lesneski (Coral Vita)
* Joe Oliver (Coral Vita)
* Dr. Joel Sokol (Georgia Tech)
* Renata Haque (Georgia Tech)
