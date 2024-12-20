# LuloBankDE
This notebook performs data analysis on TV series data retrieved from the TVMaze API.

## Installation and Requirements

1. **Python Environment:**  A Python 3.7+ environment is required.

2. **Dependencies:** Install the necessary Python packages using pip:
   ```bash
   pip install pandas requests ydata-profiling sqlite3
   ```

3. **Data Storage:** Ensure you have write permissions to the folder where you intend to save files. The script saves the downloaded JSON files to a local folder called `json`, and the parquet and sqlite database file to a local folder called `data`.


## Functionality overview

This notebook performs the following actions:

1. **Data Acquisition:** Collects data for every day of January 2024 from the TVMaze API. Each day's data is saved in a separate JSON file.

2. **JSON to DataFrame:** Processes JSON files to create pandas DataFrames, preserving data integrity.

3. **Data Profiling:** Generates a data profile report using `ydata-profiling` to analyze data quality, identify missing values, and other important statistics.

4. **Data Cleaning:** Cleans the dataframes, including removing columns with more than 70% null values, converting data types and handling missing values. Creates separated tables for shows, episodes and webchannels.

5. **Data Storage:** Saves the cleaned dataframes as parquet files with snappy compression. Saves the processed data into a SQLite database.

6. **Data Aggregation:** Performs aggregations on the parquet data to get statistics, such as average runtime, show counts by genre, and unique web domains for shows.

## Code details:

The code includes functions to handle each step of the process:


* `data_request`: Retrieves data from a given URL for a specified date.
* `json_to_dataframe`: Processes JSON data and creates a DataFrame.
* Other utility functions: process data, store it in different files and performs aggregations.

## Output Files:

* `json/*.json`: Files containing raw JSON data from the API.
* `data/episodes.parquet`, `data/shows.parquet`, `data/webchannel.parquet`: Parquet files of the processed data.
* `profiling_series_2024.html`: HTML file containing the profiling report.
* `pruebade.db`: SQLite database file


## Author

Vanessa Movilla
