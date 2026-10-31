YouTube Trending Videos: Multi-Country Data Analysis with Pandas

For this course project we analyzed trending YouTube videos from ten countries using pandas. The work is a set of 15 data-wrangling tasks: load and clean the country files, combine them into one table, then answer questions about tags, channels, views, likes and video categories.

Everything is in one notebook: CS-Final-Project.ipynb.

The data

Ten CSV files, one per country (Canada, Germany, France, Great Britain, India, Japan, Korea, Mexico, Russia, USA), plus one JSON file per country that maps category_id to a category name. It looks like the public "Trending YouTube Video Statistics" dataset from Kaggle, so double-check the source and add a link here.

Each row is one video on one trending day, with columns like video_id, trending_date, title, channel_title, category_id, publish_time, tags, views, likes, dislikes, comment_count, and flags for disabled comments, disabled ratings and removed videos.

Combined, the ten files have 375,942 rows. The notebook expects this layout:

CSV_Files/    CAvideos.csv, DEvideos.csv, FRvideos.csv, ...
Json_Files/   CA_category_id.json, DE_category_id.json, ...
What we did

Cleaning

Filled the missing description values with "No description"
Read the Mexican, Japanese, Korean and Russian files with different encodings, because they came out as unreadable text with the default settings
Added a Country column to each file and stacked all ten into one dataframe

The 15 tasks

Combine all CSVs into one dataframe with a country column
Find videos with no tags
Total views per channel
Move videos with disabled comments, disabled ratings or errors into an excluded dataframe and remove them from the main one (this dropped the table from 375,942 to 362,285 rows)
Add a like_ratio column (likes divided by dislikes)
Group publish times into 10-minute intervals
For each interval: number of videos, average likes, average dislikes
Count videos per tag
Find the most common tag (it was "funny", with 14,940 videos)
Average like ratio per (tag, country)
Most-viewed video for each (trending date, country)
Split trending_date into year, month and day
Most-viewed video for each (month, country)
Read all the category JSON files into one dataframe
Count videos with a non-assignable category, per country

Running it
bash
git clone https://github.com/<your-username>/youtube-trending-analysis-pandas.git
cd youtube-trending-analysis-pandas
pip install pandas numpy jupyter
jupyter notebook CS-Final-Project.ipynb

Make sure the CSV_Files/ and Json_Files/ folders sit next to the notebook.

Team

Davina David and Abdul Sami 
