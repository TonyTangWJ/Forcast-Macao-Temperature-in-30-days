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
## Feature Engineering

The dataset was enhanced with rolling statistics and differential features across all weather metrics:

### Temperature Features
- **Rolling averages** (3-day and 7-day windows):
  - `Temp_Max_3`, `Temp_Max_7`
  - `Temp_Min_3`, `Temp_Min_7`
  - `Temp_Avg_3`, `Temp_Avg_7`
- **Differential features**:
  - `Temp_Diff_Max_Avg`: (Max - Avg)
  - `Temp_Diff_Min_Avg`: (Min - Avg)
  - `Temp_Diff_Max_Min`: (Max - Min)

### Dew Point Features
- **Rolling averages** (3-day and 7-day windows):
  - `Dew_Max_3`, `Dew_Max_7`
  - `Dew_Min_3`, `Dew_Min_7`
  - `Dew_Avg_3`, `Dew_Avg_7`
- **Differential features**:
  - `Dew_Diff_Max_Avg`: (Max - Avg)
  - `Dew_Diff_Min_Avg`: (Min - Avg)
  - `Dew_Diff_Max_Min`: (Max - Min)

### Humidity Features
- **Rolling averages** (3-day and 7-day windows):
  - `Humidity_Max_3`, `Humidity_Max_7`
  - `Humidity_Min_3`, `Humidity_Min_7`
  - `Humidity_Avg_3`, `Humidity_Avg_7`
- **Differential features**:
  - `Humidity_Diff_Max_Avg`: (Max - Avg)
  - `Humidity_Diff_Min_Avg`: (Min - Avg)
  - `Humidity_Diff_Max_Min`: (Max - Min)

### Wind Features
- **Rolling averages** (3-day and 7-day windows):
  - `Wind_Max_3`, `Wind_Max_7`
  - `Wind_Min_3`, `Wind_Min_7`
  - `Wind_Avg_3`, `Wind_Avg_7`
- **Differential features**:
  - `Wind_Diff_Max_Avg`: (Max - Avg)
  - `Wind_Diff_Min_Avg`: (Min - Avg)
  - `Wind_Diff_Max_Min`: (Max - Min)

### Pressure Features
- **Rolling averages** (3-day and 7-day windows):
  - `Pressure_Max_3`, `Pressure_Max_7`
  - `Pressure_Min_3`, `Pressure_Min_7`
  - `Pressure_Avg_3`, `Pressure_Avg_7`
- **Differential features**:
  - `Pressure_Diff_Max_Avg`: (Max - Avg)
  - `Pressure_Diff_Min_Avg`: (Min - Avg)
  - `Pressure_Diff_Max_Min`: (Max - Min)
