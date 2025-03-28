Set up Postgres, PowerBI and VS Code. 
Set up the Postgres database using pgadmin4. 

Created Species, Countries, Individuals, Tracking_devices and Observations tables using query tool in pgadmin 4 postgres. 
* Species - gives species data about the core species (in this case the jaguar).
* Countries - stores countries (countries will be extrapolated from the longitude and latitude data using a python script)
* Individuals - gives information about individuals in the jaguar study, their ID, F/M and estimated age.
* Tracking_devices - gives information on the tracking device types (all were GPS but were differing types of trackers). Each jaguar has a tracking ID.
* Observations - gives location, device ID, individual ID, date and time. Allows for extrapolation of geography data and migration patterns tracking. 

I modified the SQL tables: 
* Remove deployment_date column from tracking_devices
* Add (jaguar) weight to individuals table
* Removed timestamp from observations table and added separate time and date columns instead - allows for easier parsing of data.

Cleaned the Excel data:
* Removed collar_brand column for tracking devices (not relevant for my project aims)
* Changed timestamp to date and time column
* Removed study name column (it is the same for the entire dataset)

Set up Pycharm environment. Installed pandas, numpy and scipy - needed terminal debugging (powershell/Windows and Pycharm terminal) due to several PATH and directory errors. I then loaded the CSV data files sourced from Movebank. This required install of csv editor plugin due to Pycharm having difficulty reading the file. 
