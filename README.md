# Nepal Earthquake Magnitude Data Analysis

A comprehensive analysis of earthquake magnitude data in Nepal from 1994 to 2019, sourced from the Nepal Seismic Center.

## Project Overview

This project scrapes, cleans, and analyzes earthquake data from Nepal's seismic activity over a 25-year period. The analysis includes data visualization, magnitude trends, and geographic distribution of earthquakes across different epicenter regions.

## Data

### Source
- Data is scraped from the Nepal Seismic Center website: http://seismonepal.gov.np/earthquakes/

### Files
- **`np_earthquake_unclean.csv`** - Raw earthquake data as scraped from the source (965 records)
- **`earthquake.csv`** - Cleaned and processed earthquake data ready for analysis
- **`extract_data.ipynb`** - Data extraction and cleaning pipeline

### Data Features
- **Date/Time**: Earthquake timestamp (converted from Nepali calendar format)
- **Latitude/Longitude**: Geographic coordinates of epicenter
- **Magnitude (ML)**: Local magnitude of the earthquake
- **Epicenter**: District/region name in Nepal

## Data Cleaning

The cleaning process includes:
1. Web scraping earthquake records from annual pages (1994-2019)
2. Parsing dates from Nepali calendar (B.S.) to Gregorian calendar (A.D.)
3. Standardizing time formats
4. Removing duplicate and invalid entries
5. Filtering out earthquakes outside Nepal borders
6. Correcting coordinate errors for specific regions

## Notebooks

### `extract_data.ipynb`
Handles complete data extraction and cleaning pipeline:
- Fetches data from multiple years
- Parses and standardizes date/time formats
- Validates geographic coordinates
- Exports cleaned dataset as CSV

### `Nepal_Earthquake_Magnitude_Data_Analysis_and_Visualization.ipynb`
Comprehensive analysis including:
- Earthquake magnitude distribution and statistics
- Temporal trends in seismic activity
- Geographic distribution across regions
- Visualizations (histograms, maps, time series plots)

## Usage

### Requirements
- Python 3.7+
- pandas
- numpy
- matplotlib
- seaborn
- scipy
- requests

### Getting Started

1. Clone or navigate to the project directory
2. Open the notebooks in Jupyter:
   ```bash
   jupyter notebook extract_data.ipynb
   jupyter notebook Nepal_Earthquake_Magnitude_Data_Analysis_and_Visualization.ipynb
   ```
3. Run cells to extract, clean, and analyze the data

### Using the Cleaned Data

```python
import pandas as pd

# Load the cleaned dataset
df = pd.read_csv('earthquake.csv')

# Display basic info
print(df.head())
print(df.info())
print(df.describe())
```

## Key Findings

- Analysis covers **965 earthquake events** in Nepal from 1994-2019
- Data includes latitude, longitude, magnitude, and epicenter information
- Earthquakes distributed across multiple districts/regions in Nepal
- Magnitude range varies from ~4.0 to ~6.0 on the local magnitude scale

## Project Structure

```
Nepal_earthquake/
├── README.md
├── extract_data.ipynb                                        # Data extraction & cleaning
├── Nepal_Earthquake_Magnitude_Data_Analysis_and_Visualization.ipynb  # Analysis
├── earthquake.csv                                            # Cleaned data
└── np_earthquake_unclean.csv                               # Raw data
```

## Notes

- Some epicenter coordinates were corrected based on geographic validation
- Events outside Nepal (India, Bangladesh, Bhutan, Tibet) were filtered out
- Missing epicenter data for some events was handled based on coordinate validation
- The dataset represents the most complete historical earthquake record available from the Nepal Seismic Center

## License

This project uses publicly available data from the Nepal Seismic Center (http://seismonepal.gov.np/)
