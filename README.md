# Forcast-Macao-Temperature-in-30-days
##1. Catch_data.ipynb
   1.1 Crawl the data from weather underground (2001.01.01-2025.03.28), and then save it to csv file.
##2. Process_data.ipynb
   **2.1 Set the index as datatime format
   **2.2 Feature 'Temp_Min' has several zero values. Substitute it by (2\*Temp_Avg - Temp_Max), and substitute the value lower than 30 to 30.
   **2.3 Feature 'Dew_Min' has several zero values. Substitute it by (2\*Dew_Avg - Dew_Max), and substitute the value lower than 10 to 10.
   **2.4 Feature 'Humidity_Min' has several zero values. Substitute it by (2\*Humidity_Avg - Humidity_Max), and substitute the value lower than 20 to 20.
   **2.5 Convert 'Wind_Max' >= 50 to 50.
   **2.6 Convert 'Pressure_Avg' <27.3 to 27.3, and then convert Pressure_Min = 0 to the average of the other two。
##3. 
