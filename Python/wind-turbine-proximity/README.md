
# Wind Turbine Proximity Analysis – Berlin Region

This project investigates the proximity of wind turbines to administrative district centers in Berlin. The objective is to assess which turbines are located within 5 km of any district centroid, a simple metric that could be relevant for urban planning, environmental studies, or policy-making regarding renewable energy installations.

## Project Objectives

- Load and visualize wind turbine data in Berlin.
- Calculate the distance between each wind turbine and the nearest district centroid.
- Identify turbines located within a 5 km radius of a district center.
- Visualize the result using an interactive map with color-coded proximity.
- Plot and analyze the distribution of distances using a histogram.
- Summarize basic statistics such as min, max, and average distances.

## Key Outputs

- `wind_turbines_proximity_final.html`: Interactive map showing turbines within 5 km.
- `distance_histogram.png`: Histogram showing distribution of distances.
- Console output with:
  - Number of turbines within 5 km
  - Average distance
  - Minimum and maximum distances

## Data Sources

- **Wind Turbine Data:** Extracted using [Overpass Turbo](https://overpass-turbo.eu/)
- **Berlin District Boundaries (Bezirksgrenzen):** (https://daten.odis-berlin.de/en/dataset/bezirksgrenzen/)

