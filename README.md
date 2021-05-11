# Investigate-a-dataset

## Project: TMDB Data Analysis
### Table of Contents

    Introduction
    Data Wrangling
    Exploratory Data Analysis
    Conclusions

### Introduction

TMDB (The Movie DataBase) is a dataset that contains data about movies. These data were collected from the community. Each movie has some interesting attributes such as:
<ul>
    <li>original title
    <li>genres
    <li>cast
    <li>director
    <li>release year
    <li>budget
    <li>revenue
    <li>rating
</ul>
To get an insight on the different data patterns, I'll try to breakdown the dataset and answer some question, such as:
<ol>
    <li>Which genres are most popular from year to year?
    <li>Most popular actor from year to year?
    <li>Did movies with higher vote count received a better rating?
    <li>What kinds of properties are associated with movies that have high revenues?
    <li>How did the number of film production changed over time?
</ol>
### Data Wrangling

In this section of the report, I will load in the data, check for cleanliness, and then trim and clean the dataset for analysis.


### Data Cleaning

The dataset contains some columns that aren't useful for my investigation. To simplify the analysis, I'll remove these columns:

1. imdb_id
2. homepage
3. tagline
4. release_date
5. overview
6. keywords



Upon a deeper look into the dataset, there're movies with some important values such as budget, and revenue set to 0. This is unrealistic and can't be analyized. Thus, any movie with 0 value in one, or more of these columns ("budget_adj", "revenue_adj", "budget", "revenue", "runtime") will be removed.

Additionally, columns ("cast", "directors", "genres", "production_companies") have enteries seperated by "|". These could be problematic when trying to extract the different entities within one entery. Thus, the entities in one entery will be seperated into different columns to ease the data exploration process.


### Conclusions

Afetr cleaning the data, I was able to answer the research questions:
##### Question 1: Which genres are most popular from year to year?

Throughout the different years, 'Drama' seems to be the most popular genre.
##### Question 2: Most popular actor from year to year?

The table showed some of the biggest names in Hollywood, and when was their peak.
##### Question 3: Did movies with higher vote count received a better rating?

Not quite true. The corralation doesn't indicate a strong relationship between vote counts and higher vote average.
##### Question 4: What kinds of properties are associated with movies that have high revenues?
<table>
    <tr><th>Popular director</th> 	<td>Steven Spielberg</td></tr>
    <tr><th>Popular actor</th> 	<td>Robert De Niro</td></tr>
    <tr><th>Popular genre</th> 	<td>Drama</td></tr>
    <tr><th>Production Company</th> 	<td>Universal Pictures</td></tr>
    <tr><th>Release year</th> 	<td>2011</td></tr>
    <tr><th>Average budget</th> 	<td>47,896,614</td></tr>
    <tr><th>Average Revenue</th> 	<td>184,138,833</td></tr>
    <tr><th>Average vote</th> 	<td>6.29</td></tr>
</table>
##### Question 5: How did the number of film production changed over time?

There's a significant increase in the number of movies produced each year.
#### Limitations

In the cleaning stage, many movies were discarded due to insuffecient data given. The original dataset contained 10,866 movie entry, and the cleaned data set contains 3,805; this means almost 65% of the enteries were discarded. Of course this will have an effect on all the answers found, for instance the number of movies produced each year may not accuratly represent the actual case, in case more movies from certain years were discarded than the other years.

In the revenue data, there was no normalization, exchange rate, or currency conversion considered during the nalysis. The analysis was limited to the given numerical values.

