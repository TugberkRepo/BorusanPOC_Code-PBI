# EV Charging Station Optimization Project
This repository contains the complete workflow for optimizing the placement and capacity of EV charging stations in Istanbul, Turkey. The goal of this project is to meet the rising demand for electric vehicle (EV) infrastructure while minimizing costs, using a combination of data analysis, optimization techniques, and PowerBI visualizations.

## Table of Contents
* Installation
* Project Overview
* Data Files
* Code Workflow
* Optimization Model
* Results & Visualizations
* Acknowledgements

## Installation
To install the required dependencies, you can use:
pip install pulp pandas numpy geopy

## Project Overview
This project was developed in collaboration with Borusan Otomotiv, the official importer of BMW vehicles in Turkey. With the increasing adoption of EVs in the region, Borusan required an optimized plan for placing EV charging stations throughout Istanbul.

### Key Objectives:

* Optimize charging station locations and capacities.
* Ensure that demand in each district is met based on population and EV adoption rates.
* Minimize the total cost of deploying and operating the stations.

## Data Files
### Key data used:
* 2019-yıl-belediye-nüfuslar.xlsx: Contains population data for districts in Istanbul.
* BorusanSON.xlsx: A dataset that includes location and capacity details for the planned charging stations.
* turkey-geo.json: A geoJSON file providing geographical data (district names, coordinates).
* filtered_stations.xlsx: Final optimized locations and capacities for EV charging stations after optimization.

## Visualizations:
Several PowerBI dashboards were created for presenting the results, including:

* Capacity distribution per district.
* Percentage share of stations and capacity in each district.
* Map visualization of station locations with their respective capacities.

## Code Workflow
The following steps outline the workflow of this project:

**Data Loading and Preprocessing:**
Data related to Istanbul's districts, population, and station locations were extracted and cleaned. District coordinates and population data were merged to calculate the demand for EV charging stations.

**Demand Calculation:**
Using the population and vehicle ownership rates, the demand for charging stations in each district was calculated. Key assumptions include:

* Vehicle ownership rate: 25%
* EV penetration rate: 2%
* Market share of Borusan: 20%
* Capacity of one station: 20 vehicles/day

**Optimization Model:**
A linear programming model was developed using the PuLP library. The model aims to minimize the total cost while ensuring that all districts' demands are met.

**Joining Data:**
The station and population datasets were merged based on the district names, allowing for further analysis and optimization of station locations.

**Final Results:**
The optimized locations of the stations were exported into filtered_stations.xlsx for further analysis and visualization.

## Optimization Model
### Parameters:
* **Demand:** Calculated based on the population and EV ownership rates.
* **Capacity:** The number of vehicles a station can serve per day.
* **Fixed Costs:** Costs associated with setting up a station.
* **Distance Threshold:** A station can only serve districts within a 5 km radius.

### Constraints:
* **Demand Satisfaction:** Ensure that each district's demand is fully met.
* **Capacity Limits:** Each station has a capacity constraint that cannot be exceeded.
* **Service Distance:** A station can only serve districts within a defined radius.
* **Utilization Balance:** Ensure stations are neither underutilized nor overloaded.

## Results and Visualizations
### Key Outputs:
**1. Optimal Stations and Capacities:**
The solution provided the best locations for stations, with detailed capacity requirements for each.

**2. Visualization with PowerBI:**

**Map of Station Locations:** Each charging station is shown on a map of Istanbul, with its capacity visualized using bubble sizes (see screenshots in the repository).

**District-wise Distribution:** Pie charts and bar graphs were used to display the capacity and station distribution across various districts (see MultipleDistrict-Filtre.png, DAX- Percentage of Total Capacity.png).

**Station Performance:** The dashboards offer insights into the performance and usage of each station.
