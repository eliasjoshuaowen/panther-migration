Set up Postgres, PowerBI and VS Code. 
Set up the Postgres database using pgadmin4. 

Created Species, Countries, Individuals, Tracking_devices and Observations tables using query tool in pgadmin 4 postgres. 
* Species - gives species data about the core species (in this case the jaguar).
* Countries - stores countries (countries will be extrapolated from the longitude and latitude data using a python script)
* Individuals - gives information about individuals in the jaguar study, their ID, F/M and estimated age.
* Tracking_devices - gives information on the tracking device types (all were GPS but were differing types of trackers). Each jaguar has a tracking ID.
* Observations - gives location, device ID, individual ID, date and time. Allows for extrapolation of geography data and migration patterns tracking. 

I modified the SQL tables in pgadmin4: 
* Remove deployment_date column from tracking_devices
* Add (jaguar) weight to individuals table
* Removed timestamp from observations table and added separate time and date columns instead - allows for easier parsing of data.

Cleaned the Excel data:
* Removed collar_brand column for tracking devices (not relevant for my project aims)
* Changed timestamp to date and time column
* Removed study name column (it is the same for the entire dataset)

Set up Pycharm environment. Installed pandas, numpy and scipy - needed terminal debugging (powershell/Windows and Pycharm terminal) due to several PATH and directory errors. I then loaded the CSV data files sourced from Movebank. This required install of CSV editor plugin due to Pycharm having difficulty reading the file. 
* Started writing the Python code in Pycharm to read the CSV
* In Python, extracted latitude and longitude data
* Built KDTree for spatial data
* Created function find_nearest_town which searches for a point in the tree nearest to a given latitude and longitude, selects matching row in df using df.iloc[idx] and returns nearest town name, region code, and country code 
* Received name errors so neededto clean columns using str.strip() and assert to test
* I then used a for try except loop to iterate through the dataframe to process each row and print for any errors. I then exported the results to a CSV file.
* I cleaned up a few typos in the CSV file. The CSV file was now ready for use.
