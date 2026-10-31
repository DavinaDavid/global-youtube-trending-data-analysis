# YouTube Trending Videos: Multi-Country Data Analysis with Pandas

For this course project we analyzed trending YouTube videos from ten countries using pandas. The work is a set of 15 data-wrangling tasks: load and clean the country files, combine them into one table, then answer questions about tags, channels, views, likes and video categories.

Everything is in one notebook: `CS-Final-Project.ipynb`.

## The data

Ten CSV files, one per country (Canada, Germany, France, Great Britain, India, Japan, Korea, Mexico, Russia, USA), plus one JSON file per country that maps `category_id` to a category name.

Source: _add the dataset link here_

Each row is one video on one trending day, with columns like `video_id`, `trending_date`, `title`, `channel_title`, `category_id`, `publish_time`, `tags`, `views`, `likes`, `dislikes`, `comment_count`, and flags for disabled comments, disabled ratings and removed videos.

Combined, the ten files have 375,942 rows. The notebook expects this layout:

```
CSV_Files/   CSV file of each country data
Json_Files/   Json file of each country data
CS-Final-Project.ipynb The final Notebook
```

## What we did

### Cleaning

- Filled missing `description` values with "No description"
- Read the Mexican, Japanese, Korean and Russian files with different encodings, because they came out as unreadable text with the default settings
- Added a `Country` column to each file and stacked all ten into one dataframe

### The 15 tasks

1. Combine all CSVs into one dataframe with a country column
2. Find videos with no tags
3. Total views per channel
4. Move videos with disabled comments, disabled ratings or errors into an `excluded` dataframe and remove them from the main one (375,942 rows down to 362,285)
5. Add a `like_ratio` column (likes divided by dislikes)
6. Group publish times into 10-minute intervals
7. For each interval: number of videos, average likes, average dislikes
8. Count videos per tag
9. Find the most common tag (it was "funny", with 14,940 videos)
10. Average like ratio per (tag, country)
11. Most-viewed video for each (trending date, country)
12. Split `trending_date` into year, month and day
13. Most-viewed video for each (month, country)
14. Read all the category JSON files into one dataframe
15. Count videos with a non-assignable category, per country


## Running it

```bash
git clone https://github.com/DavinaDavid/youtube-trending-analysis-pandas.git
cd youtube-trending-analysis-pandas
pip install pandas numpy jupyter
jupyter notebook CS-Final-Project.ipynb
```

Make sure the `CSV_Files/` and `Json_Files/` folders sit next to the notebook.

## Team

Davina David and Abdul Sami
