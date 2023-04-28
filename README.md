# SQLalchemy-Challenge

# SQLAlchemy - Surfs Up!
This project uses Python and SQLAlchemy to do basic climate analysis and data exploration of the climate database. All analysis is done using SQLAlchemy (ORM queries), Pandas, and Matplotlib. It also provides an API (designed using Flask) for querying this climate data.

![image](https://user-images.githubusercontent.com/120751287/235059372-eca91314-8671-4224-a70a-3b8280550c8a.png)

## Part 1: Analyze and Explore the Climate Data

1. Use the provided files `climate_starter.ipynb` and `Resources/hawaii.sqlite` files to complete my climate analysis and data exploration.

2. Use SQLAlchemy `create_engine` to connect to my SQLite database.

3. Use SQLAlchemy `automap_base()` to reflect my tables into classes and save a reference to those classes called `Station` and `Measurement`.

4. Link Python to the database by creating a SQLAlchemy session.

## Precipitation Analysis

1. Find the most recent data in the dataset. 

2. Using that date, get the previous 12 months of precipitation data by querying the previous 12 months of data.

3. Select only the `date` and `prcp` values.

4. Load the query results into a Pandas DataFrame. Explicitly set the column names.

5. Sort the DataFrame values by `date`.

6. Plot the results using the DataFrame `plot` method, as the following image shows below:

 ![Precipitation_Plot](https://user-images.githubusercontent.com/120751287/235060620-bcc95f5d-c479-4236-a0bc-b13d0fdb97f0.png)

7. Use Pandas to print the summary statistics for the precipitation data.

## Station Analysis

1. Design a query to calculate the total number of stations in the dataset.

2. Design a query to find the most-active stations (that is, the stations that have the most rows). To do so, complete the following steps:.

    * List the stations and observation counts in descending order.

      * Answer the following question: 
  
    * Which station id has the greatest number of observations?

3. Design a query that calculates the lowest, highest, and average temperatures that filters on the most-active station id found in the previous query.

4. Design a query to get the previous 12 months of temperature observation (TOBS) data. To do so, complete the following steps:

    * Filter by the station that has the greatest number of observations.

    * Query the previous 12 months of TOBS data for that station.

    * Plot the results as a histogram with bins=12, as the following image shows below:
    
![Temperature_Plot](https://user-images.githubusercontent.com/120751287/235062158-376e9b7a-c2dd-4900-b0dc-fa602e7e7f21.png)

5. Close my session.

## Step 2 - Design My Climate App
This part of the project surfaces several SQLAlchemy precipitation and temperature queries in an API using a Python Flask app:

* Use Flask to create my routes.

### Routes

1. `/`

    * Home page.

    * List all available routes.

2. `/api/v1.0/precipitation`

    * Convert the query results from your precipitation analysis (i.e. retrieve only the last 12 months of data) to a dictionary using `date` as the key and `prcp` as the value.

    * Return the JSON representation of your dictionary.

3. `/api/v1.0/stations`

    * Return a JSON list of stations from the dataset.

4. `/api/v1.0/tobs`
  
    * Query the dates and temperature observations of the most-active station for the previous year of data.
  
    * Return a JSON list of temperature observations (TOBS) for the previous year.

5. `/api/v1.0/<start>` and `/api/v1.0/<start>/<end>`

    * Return a JSON list of the minimum temperature, the average temperature, and the maximum temperature for a specified start or start-end range.

    * For a specified start, calculate  `TMIN`, `TAVG`, and `TMAX` for all the dates greater than or equal to the start date.

    * For a specified start date and end date, calculate  `TMIN`, `TAVG`, and `TMAX` for the dates from the start date to the end date, inclusive.
