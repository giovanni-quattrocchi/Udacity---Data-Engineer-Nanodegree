
## Summary of the project

By the needs of Sparkify, has been requested to create design and model a Postgres database collecting data songns and data user activity on their new music streaming app in order to optimize queries on song play analysis, creating tables to host the data source and creating the orchestration of ETL pipeline to move data source to the target tables modelled.
In particulary has been define a star schema datamart on database with the following tables:

### Fact Table
- songplays (records in log data associated with song plays i.e. records with page NextSong): songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent
### Dimension Tables
- users (users in the app): user_id, first_name, last_name, gender, level
- songs (songs in music database): song_id, title, artist_id, year, duration
- artists (artists in music database): artist_id, name, location, latitude, longitude
- time (timestamps of records in songplays broken down into specific units): start_time, hour, day, week, month, year, weekday

## Definition of file in the repository

- \data: contains data source of songs and user activities
- create_tables.py: drops and creates target tables. Run this file to reset target tables before each time run the ETL scripts.
- sql_queries.py: contains all sql queries, and it is used by the create_table and etl scripts.
- etl.py: reads and processes files from song_data and log_data and loads them into target tables.

## RunBook

1. launch create_tables.py script on terminal (make sure you are in the same path of the script) : python create_tables.py
2. launche etl.py script on terminal (make sure you are in the same path of the script): python etl.py
