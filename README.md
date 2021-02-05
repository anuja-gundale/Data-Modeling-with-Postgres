# Project description
* A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analytics team is particularly
  interested in understanding what songs users are listening to. Currently, they don't have an easy way to query their data, which resides in a directory of JSON logs on user
  activity on the app, as well as a directory with JSON metadata on the songs in their app.

* The goal of SparkifyDB is to serve as a database for storing information that is extracted from the log and song data json files.

# Dataset:
  * Song Dataset : Song files are in json format and are nested  in subdirectories under /data/song_data.
  * Log Dataset: Log files are in jsone format and are nested  in subdirectories under /data/log_data.

# Database schema:

 * Fact Table : 
   * songplays - records in event data associated with song plays i.e. records with page 'NextSong'
      * Columns: songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent

* Dimension Tables
  * users - users in the app
    * Columns : user_id, first_name, last_name, gender, level

  * songs - songs in the app
    * Columns : song_id, title, artist_id, year, duration
    
  * artists - artists in the app
    * Columns : artist_id, name, location, lattitude, longitude
    
   * time - timestamps of records in songplays broken down into specific units
      * Columns : start_time, hour, day, week, month, year, weekday

# ETL Pipeline:
There are three main scripts:

* create_tables.py: Creates the star schema.
* sql_queries.py: Captures all the SQL queries used for creating the schema and inserting the data.
* etl.py: Implements the ETL pipeline by extracting data from song and log data files and inserts them into tables.
