# Bird-Clustering
# Project #3 - Illinois Bird Migration Patterns

## Team: Autobird
### John Leigh, Jessica Greco, Michael O'Leary, Connor Thomas, Paul Brown

## Project Summary
In this project we focused on visualizing data about bird sightings in Illinois. We chose 10 different species, many of which were endangered or at-risk in recent history, and displayed the bird sighting data associated with each species. The bird sighting data we used to make these visualizations is made publically available through Cornell's eBird website.

The steps used to create this visualization were: 
1.  Download the .CSV formatted raw data from eBird (Cornell)
2.  Perform an ETL on the .CSV to ensure it was ready for analysis
  * This included dropping unused columns, converting date formats, and creating an index column with unique, sequential values as our Primary Key
3.  Populate a sqlite database with the cleanbird.csv data 
4.  Use Flask to define API endpoints for our javascript files to reference and pull data from
  * the Flask routes return sql queries of our sqlite database using sqlalchemy and return the data in JSON format using the jsonify(data) function
5.  Create a javascript file that creates data visualizations using Leaflet.js and Plotly.js. Data was accessed from our API endpoints using D3.js

The applications, libraries and tools that we used include:
- Applications
  - VS Code
  - SQLite3
  - Flask
  - Excel

- Libraries
  - jquery
  - Bootstrap
  - Leaflet.js
  - Plotly.js
  - StadiaMaps
  - D3.js
  - Pandas (Python)
  - SQLAlchemy


**INSTRUCTIONS FOR RUNNING THE PROGRAM ON YOUR LOCAL MACHINE**
1.  Ensure cleanbird.csv has dates in YYYY-MM-DD format (note that github cannot store a file this large, so you must download it from the cleanbird.csv repo link below)
2.  Run etl_all_columns.ipynb and etl_selected_columns.ipynb
3.  In the integrated terminal, run this command: python bird_alchemy.py
   * Note: you will need to install both flask and flask-CORS in order to run this
4.  Once the flask app is up and running, open up final-index.html in file explorer and click on the icon to open the app in Chrome

### Data Sources:
- eBird API : https://documenter.getpostman.com/view/664302/S1ENwy59#intro 
- Visualization examples : https://science.ebird.org/en/status-and-trends 
- Illinois Audubon Society : https://illinoisaudubon.org/springmigrationdashboard/ 
- Birdcast : https://dashboard.birdcast.info/region/US-IL-031 
- eBird overview page: https://science.ebird.org/en/status-and-trends
- eBird abundance animations: 
  - https://science.ebird.org/en/status-and-trends/abundance-animations 
  - https://science.ebird.org/en/status-and-trends/abundance-animations 
- eBird Trends Map: https://science.ebird.org/en/status-and-trends/trends-maps
- eBird ShorebirdViz:  https://shorebirdviz.ebird.org/species/ameavo?week=1
- Endangered Species List : https://www.audubon.org/climate/survivalbydegrees/state/us/il 


## Steps
### Finding data sources, scraping data
### Creating a Jupyter Notebook ETL to read CSV files into SQLite
To start, we created two .ipynb files to web scrape publiclly available data regarding bird migrations. The data was then merged, cleaned, and written to a CSV file: cleanbird.  The data was then read into a a SQLite database using etl_selected_columns.ipynb.

cleanbird.csv file repo (too large for github): https://drive.google.com/file/d/1D9gYqRMf75FjYv41oDJFoQ8fWJsGW2iE/view?usp=sharing 

### A Flask session was created for analysis
SQLite is being used to host the data and perform anlysis functions. bird_alchemy.py 
### Creating Flask API endpoints
Using Flask as our locally hosted database, we then created API endpoints for the future webpage to use for queries. Returned data is JSONified. We were able to connect Flask to Leaflet using Flask_CORS.
API date filter with lat/lon grouping was added.
### Creating an interacive HTML layout 
### Creating JavaScript instructions to relay dynamic data visualization
### Using D3 to retrieve data from the Flask server
### Using Plotly to visualize the retrieved data
### Creating a grayscale basemap using Leaflet
Using StadiaMap, we created a basemap and connected it to the API.
### Overlaying plotted data and metadata on basemap 
Density data was then plotted using latitude and longitude, and grouped by species. A dropdown box allows the user to select the species and a horizontal slider allows the user to select the date range from either endpoint. The webpage uses D3 to connect to Flask, which queries our SQLite database to populate the map and metadata.
### Markers and Popup Data
The legend was added to the map, using a CSS file. The marker size is based on density. Marker popups were added to include Species, Location, Date Observed, and Time Observed. 
### Debugging, Debugging, and more Debugging

