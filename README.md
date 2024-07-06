# sqlalchemy-challenge
---

This challenge demonstrates how to analyze climate data using Python and SQLAlchemy, and how to expose the analysis results via a Flask API. The Jupyter notebook provides the initial analysis, while the Flask app provides a way to interact with the data programmatically.


# Climate Analysis and Flask API

This challenge involves analyzing climate data using Python, SQLAlchemy, and Flask. The analysis is performed in a Jupyter notebook (`climate_starter.ipynb`), and a Flask API (`app.py`) is created to expose the analysis results via various endpoints.

## Files Included

- `climate_starter.ipynb`: A Jupyter notebook used for the initial analysis of the climate data.
- `app.py`: A Flask application that serves the analysis results via various API endpoints.


## climate_starter.ipynb

This Jupyter notebook performs the following tasks:

1. **Database Setup**:
    - Connects to the SQLite database containing the climate data.
    - Reflects the database tables using SQLAlchemy.

2. **Exploratory Analysis**:
    - Retrieves and analyzes the most recent 12 months of precipitation data.
    - Identifies the most active weather stations.
    - Retrieves temperature observations for the most active station for the last year of data.

3. **Statistical Analysis**:
    - Calculates summary statistics for the temperature observations.
    - Defines functions to calculate temperature summaries for given start and end dates.

## app.py

This Flask application exposes the results of the climate analysis via several API endpoints:

### Available Routes

- **/**: Home page listing all available routes.

- **/api/v1.0/precipitation**: 
  - Retrieves the last 12 months of precipitation data.
  
- **/api/v1.0/stations**: 
  - Retrieves a list of all weather stations.

- **/api/v1.0/tobs**: 
  - Retrieves the last 12 months of temperature observations for the most active station.

- **/api/v1.0/<start>** and **/api/v1.0/<start>/<end>**: 
  - Retrieves the minimum, maximum, and average temperatures for the given start date or start and end date range.

### Example Usage

- To get the last 12 months of precipitation data, navigate to:
  ```
  http://127.0.0.1:5000/api/v1.0/precipitation
  ```

- To get the list of stations, navigate to:
  ```
  http://127.0.0.1:5000/api/v1.0/stations
  ```

- To get the last 12 months of temperature observations for the most active station, navigate to:
  ```
  http://127.0.0.1:5000/api/v1.0/tobs
  ```

- To get temperature statistics from a start date, navigate to:
  ```
  http://127.0.0.1:5000/api/v1.0/<start>
  ```

  Replace `<start>` with a date in the format `YYYY-MM-DD`.

- To get temperature statistics for a date range, navigate to:
  ```
  http://127.0.0.1:5000/api/v1.0/<start>/<end>
  ```

  Replace `<start>` and `<end>` with dates in the format `YYYY-MM-DD`.

