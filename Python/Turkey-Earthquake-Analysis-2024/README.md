# Turkey Earthquake Analysis – Real-Time Data Visualization (2024–Present)

This project analyzes and visualizes earthquake data across Turkey using real-time data from the USGS Earthquake API. It includes geospatial and statistical visualizations to explore the distribution of magnitudes, time-based patterns, and regional impacts.

---

## Dataset – USGS Earthquake API

* **Source**: [USGS Earthquake API](https://earthquake.usgs.gov/fdsnws/event/1/)
* **Data**: Earthquake events in Turkey
* **Location**: Bounding Box (Lat: 35–43, Lon: 25–45)
* **Time Range**: 2024-01-01 to today
* **Magnitude Threshold**: 3.0 and above
* **API Key**: Not required

**API Query Example**:
`https://earthquake.usgs.gov/fdsnws/event/1/query?format=geojson&starttime=2024-01-01&minlatitude=35&maxlatitude=43&minlongitude=25&maxlongitude=45&minmagnitude=3`

---

## Performed Steps

### 1. Data Collection

* Real-time earthquake data fetched from the USGS GeoJSON API using `requests`
* Converted to a structured Pandas DataFrame
* Parsed attributes: timestamp, location, coordinates, magnitude

### 2. Regional Tagging

* Custom `assign_region()` function defined to label each earthquake by Turkish geographical region
* Categories: Aegean, Mediterranean, Southeastern Anatolia, Marmara, Central Anatolia, Eastern Anatolia, Black Sea, and Outside Turkey

### 3. Time Series Analysis

* Daily time series plot for earthquake counts
* Hourly histogram of occurrences to detect temporal activity patterns

### 4. Geospatial Visualization

* **Interactive Map**: Marker clusters colored by magnitude range
* **Heatmap**: Earthquake intensity distribution across Turkey
* **Regional Map**: Earthquake locations colored by region classification

### 5. Statistical Analysis

* Bar chart of average magnitude per region
* Boxplot of magnitude distribution by region (excluding events outside Turkey)
* Dual-axis chart: average magnitude + event count per region

---

## Key Output Visualizations


| Filename                                | Description                                                                |
| --------------------------------------- | -------------------------------------------------------------------------- |
| `earthquake_time_series.png`            | Daily earthquake counts in Turkey from January 2024 to today               |
| `earthquake_magnitude_distribution.png` | Histogram showing distribution of earthquake magnitudes                    |
| `earthquakes_by_hour.png`               | Number of earthquakes by hour of the day (UTC)                             |
| `average_earthquake_by_region.png`      | Bar chart of average magnitude by region                                   |
| `distribution_magnitude_by_region.png`  | Boxplot showing spread of magnitudes per region (excluding outside Turkey) |
| `earthquake_region_stats.png`           | Dual-axis plot: average magnitude and event count per region               |
| `turkey_earthquakes_map.html`           | Interactive map with clustered markers colored by magnitude                |
| `turkey_earthquake_heatmap.html`        | Folium heatmap showing earthquake intensity across Turkey                  |
| `turkey_quakes_by_region.html`          | Map showing earthquakes color-coded by Turkish region                      |

---

### Interactive Maps

➡️ [Click here to view the map - Earthquake Map with Clusters](https://esingamze.github.io/learning-portfolio/Python/Turkey-Earthquake-Analysis-2024/turkey_earthquakes_map.html) - Click to view all recorded earthquakes on an interactive map.
➡️ [Click here to view the map - Earthquake Heatmap](https://esingamze.github.io/learning-portfolio/Python/Turkey-Earthquake-Analysis-2024/turkey_earthquake_heatmap.html) – Visualize earthquake density across Turkey
➡️ [Click here to view the map - Earthquakes by Region](https://esingamze.github.io/learning-portfolio/Python/Turkey-Earthquake-Analysis-2024/turkey_quakes_by_region.html) – Explore earthquakes by assigned region color coding.

## Requirements

Install required Python packages:

```bash
pip install pandas requests folium matplotlib seaborn
```


