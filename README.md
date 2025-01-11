# Weather Data Ingestion Pipelines

## Objective
This project implements data ingestion pipelines to fetch, clean, and store historical, current, and forecast weather data into a Microsoft SQL Server database. The pipelines are designed to run daily for seamless data updates.

---

## Data Sources
1. **OpenWeather API**:
   - Provides current weather data.
2. **Tomorrow.io API**:
   - Supplies historical and forecast weather data.
3. **Postal Code Dataset**:
   - Used to identify 10-15 representative postal codes in Toronto for weather data retrieval.

---

## Methodology
1. **Data Ingestion Pipelines**:
   - **Current Weather Data**: Fetches temperature, humidity, and wind speed for selected postal codes.
   - **Forecast Weather Data**: Retrieves detailed multi-row forecasts for each postal code.
   - **Historical Weather Data**: Extracts past weather conditions for analysis.

2. **Feature Engineering**:
   - Extracted day, month, and year from timestamps.
   - Calculated daily temperature ranges.
   - Normalized data to standardize time zones and measurements.

3. **Database Integration**:
   - Created tables in the `uploads` schema of a Microsoft SQL Server database.
   - Used Pandas' `to_sql` method for data insertion with appropriate data types.

---

## Challenges
- **API Outages**: Managed with error handling and retry mechanisms.
- **Request Frequency Limits**: Used efficient data loops to minimize API calls.
- **Time Zone Differences**: Standardized all data to a single time zone for consistency.
- **Data Cleaning**: Addressed non-standardized formats and missing values.

---

## Files
1. **Jupyter Notebooks**:
   - [Current Weather Data Pipeline](./Current%20Weather%20Data-2.ipynb)
   - [Forecast Weather Data Pipeline](./Forecast%20Weather%20Data-2.ipynb)
   - [Historical Weather Data Pipeline](./Historical%20Weather%20Data%20Final-2.ipynb)
2. **Project Report**: [Weather Data Final Report](./MMAI%205100%20Weather%20Data%20Final%20copy-1.pdf)

---

## How to Use
1. Clone this repository:
   ```bash
   git clone https://github.com/YourUsername/Weather_Data_Ingestion_Pipelines.git

