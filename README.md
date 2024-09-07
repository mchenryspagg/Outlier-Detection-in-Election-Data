# Outlier Detection in Election Data Using GeoSpatial Analysis

## Table of contents

- [About](#about)
- [Project Overview](#project-overview)
- [Task Objective](#task-objective)
- [Data Source](#data-source)
- [Analysis and Report](#analysis-and-report)
- [Results and Findings](#results-and-findings)
- [Insights](insights)
- [Limitation of Study](limitation-of-study)
- [Acknowledgements](#acknowledgements)


## About 
This project aims to investigate potential voting irregularities in Nigeria's 2023 general election where the Independent National Electoral Commission (INEC) has faced allegations of vote manipulation and inaccuracies. The project's objective is to ensure the transparency and integrity of the election results by identifying outlier polling units where voting results significantly deviate from neighboring units.

Using geospatial analysis, the project will focus on comparing the votes each party received across polling units in one of the states in Nigeria - specifically for ANAMBRA state as per this project. By calculating an outlier score for each unit, the analysis will highlight areas with voting patterns that differ markedly from those in adjacent units. These deviations may indicate potential rigging or external influences, but they will majorly show polling units with votes widely deviating from adjacent polling units.

The project is divided into stages, with the initial stage dedicated to identifying and analyzing these outlier polling units. The results of this analysis could be instrumental in verifying the accuracy of the election outcomes and ensuring that any discrepancies are addressed. The project's findings will contribute to a broader investigation into the election's integrity, helping to uphold democratic processes.

This repository will contain the tools, code, and documentation needed to replicate the analysis and review the findings, providing transparency and facilitating further research.


## Project Overview
In the recently concluded election, the Independent National Electoral Commission (INEC) faced multiple legal challenges concerning the integrity and accuracy of the election results. Allegations of vote manipulation and irregularities have been widespread, prompting a thorough investigation into the matter.
Your mission, should you choose to accept it, is to help us uncover potential voting irregularities and ensure the transparency of the election results. You will achieve this by identifying outlier polling units where the voting results deviate significantly from neighboring units, indicating potential influences or rigging. Your keen analytical skills and attention to detail will be critical in this endeavour.

In this stage, you will focus on identifying outlier polling units based on the votes each party received. The analysis will involve geospatial techniques to find neighboring polling units and calculate an outlier score for each party in each unit. The goal is to pinpoint polling units where the voting results significantly deviate from their neighbors, indicating potential irregularities or influences.


## Task Objective
### 1.	Dataset Preparation:
-	Open the [drive link](https://drive.google.com/drive/folders/173oHgms6wYy5WKz_i3Lhl5mXcmobCWHz) and find your state of origin. If you are not a Nigerian, pick a random state.
-	Download the {YOUR_SELECTED_STATE}_crosschecked spreadsheet or CSV file.
-	If your selected dataset does not include longitude and latitude values for each polling unit or ward, use geocoding techniques to obtain them.
  
### 2.	Neighbour Identification:
-	Identify neighboring polling units based on geographical proximity. Define a radius (e.g., 1 km) to determine which units are considered neighbors.
  
### 3.	Outlier Score Calculation:
-	For each polling unit, compare the votes each party received with those of its neighboring units.
-	Calculate an outlier score for each party based on the deviation of votes from neighboring units.
-	Record the outlier scores along with the respective parties and neighboring units.
  
### 4.	Sorting and Reporting:
-	Sort the dataset by the outlier scores for each party to identify the most significant outliers.
-	Provide a detailed report explaining the methodology and findings.
-	Highlight the top 3 outliers and their closest polling units, explaining why they are considered outliers.


## Data Source
- [Link](https://drive.google.com/drive/folders/173oHgms6wYy5WKz_i3Lhl5mXcmobCWHz)


## Analysis and Report
- [Jupyter Notebook](https://github.com/mchenryspagg/Outlier-Detection-in-Election-Data/blob/main/Outlier%20Detection%20in%20Election%20Data%20Using%20Geospatial%20Analysis.ipynb)


## Results and Findings 

Based on the analysis carried out on the crosschecked election dataset for Anambra state for 3679 polling units. The geographic coordinates for 3614 of the polling units in the state were obtained from public sources. Thus, the polling units that had no latitude and longitude was dropped which made the remaining polling units as 3614.

Based on the analysis conducted, the data was grouped by LGA, and the distance between all the polling units within the LGA was determined and used to create neighboring polling units that were at a distance of 1km or less for each polling unit. This result was further broken down based on the votes by the parties at the row level.

This result led to the creation of the average votes obtained from the neighboring polling unit and this figure when compared with the vote by each party in the polling unit was used to determine an outlier score computed based on the absolute difference between the party vote from the average vote of the neighboring polling unit for that party. This result was then sorted in descending order by the outlier score and the top 3 parties with the highest outlier score were used in sorting them.

Based on these results, the top three polling units with the highest outlier scores were 04-03-03-003, 04-06-11-007, 04-03-03-005 which represents AMA-ENUGU II in ANAMBRA EAST LGA (LP) with outlier score of 477.6666667, AMAMKPU V HALL in AWKA NORTH LGA (PDP) with outlier score of 459.3333333, AMA-OKPOGBA in ANAMBRA EAST LGA (LP) with outlier score of 440.6428571.


##  Insights 
The top three polling units with the highest outlier scores were found to be 04-03-03-003, 04-06-11-007, 04-03-03-005 from the analysis carried out which represented AMA-ENUGU II in ANAMBRA EAST LGA (LP) with outlier score of 477.6666667, AMAMKPU V HALL in AWKA NORTH LGA (PDP) with outlier score of 459.3333333, and AMA-OKPOGBA in ANAMBRA EAST LGA (LP) with outlier score of 440.6428571. 

The bar plot below shows the outlier scores for each party in the top outlier polling units helping to compare the outlier scores across different polling units and parties.

![image](https://github.com/user-attachments/assets/892429c6-05c5-4050-8782-a27c55e3a20b)


The scatter plot shows the relationship between the votes and average votes of neighboring units. The size of the points represents the outlier scores. This highlights the deviation of votes in the polling units compared to their neighbors.

![image](https://github.com/user-attachments/assets/202abc96-5470-44d0-830e-e572ced9a822)


The heatmap shows the distribution of outlier scores across the polling units and parties. It provides a clear view of which polling units have the most significant deviations in votes for each party.

![image](https://github.com/user-attachments/assets/a4d88ad4-1e32-4b14-a140-9f4a88b82842)

These polling units are considered outliers due to the large difference in the votes received by the party in these polling units in comparison with the votes received by the same party in all its neighboring polling units within 1km in the same LGA. The huge difference between the votes received at these polling units for these parties when compared with the average votes received by the same party for all its neighboring polling units within 1km in the same LGA is very large when compared with similar outlier figures for other polling units and that makes these three polling units the top 3 outliers and having the top three outlier scores from all polling units analyzed from the data.

The result and the interpretation of this analysis is subject to other prevailing factors not measured in this analysis and should be subjected to further research and analysis.



## Limitation of Study
The major constraints experienced during the cause of this analysis are mainly sourcing for and obtaining the geographic coordinates (Latitude and longitude) for each polling unit. Out of 3679 polling units data obtained, only 3614 polling units geographic coordinates were obtained and the rest polling units dropped.


## Acknowledgements
This project is part of the submission requirements for stage one of the HNG 11 Internship for the Data Analyst Track. Special appreciation to the organizers of the internship - [HNG Tech](https://hng.tech/)
