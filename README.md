# Forecast Macao Temperature in 30 Days

## File Structure

1. **Catch_data.ipynb**
   - Crawls historical weather data from Weather Underground (2001.01.01 - 2025.03.28)
   - Saves the collected data to a CSV file

2. **Process_data.ipynb**
   - Performs the following data processing steps:
     - Sets the index as datetime format
     - Handles missing/abnormal values for various features:

## Data Processing Details

### Temperature Handling
- Feature: `Temp_Min`
  - Replaces zero values with: `(2 × Temp_Avg - Temp_Max)`
  - Caps minimum value at 30 (replaces values <30 with 30)

### Dew Point Handling
- Feature: `Dew_Min`
  - Replaces zero values with: `(2 × Dew_Avg - Dew_Max)`
  - Caps minimum value at 10 (replaces values <10 with 10)

### Humidity Handling
- Feature: `Humidity_Min`
  - Replaces zero values with: `(2 × Humidity_Avg - Humidity_Max)`
  - Caps minimum value at 20 (replaces values <20 with 20)

### Wind Handling
- Feature: `Wind_Max`
  - Caps maximum value at 50 (converts values ≥50 to 50)

### Pressure Handling
- Feature: `Pressure_Avg`
  - Sets minimum value at 27.3 (converts values <27.3 to 27.3)
- Feature: `Pressure_Min`
  - Replaces zero values with the average of the other pressure measurements
