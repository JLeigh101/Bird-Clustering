# Bird-Clustering
# Project #3 - Illinois Bird Migration Patterns

## Team: Autobird
### John Leigh, Jessica Greco, Michael O'Leary, Connor Thomas, Paul Brown

## Project Summary
In this project we focused on visualizing data about bird sightings in Illinois. We chose 10 different species, many of which were endangered or at-risk in recent history, and displayed the bird sighting data associated with each species. The bird sighting data we used to make these visualizations is made publically available through Cornell's eBird website.

The steps used to create this visualization were: 
1.  Download the .CSV formatted raw data from eBird (Cornell).
2.  Perform an ETL on the .CSV to ensure it was ready for analysis.
  * This included dropping unused columns, converting date formats, and creating an index column with unique, sequential values as our Primary Key.
3.  Populate a sqlite database with the cleanbird.csv data.
4.  Use Flask to define API endpoints for our javascript files to reference and pull data from.
  * the Flask routes return sql queries of our sqlite database using sqlalchemy and return the data in JSON format using the jsonify(data) function.
5.  Create a javascript file that creates data visualizations using Leaflet.js and Plotly.js. Data was accessed from our API endpoints using D3.js.
  * the visualizations plot every bird sighting as defined by user-input parameters. We filter based on species and date range, and return the lat/lon associated with     all matching bird sighting entries.
7.  Index the .html and manage styling in final-index.html and markers.css.

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
1.  Ensure cleanbird.csv has dates in YYYY-MM-DD format (note that github cannot store a file this large, so you must download it from this google drive link): https://drive.google.com/file/d/1D9gYqRMf75FjYv41oDJFoQ8fWJsGW2iE/view?usp=sharing 
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

