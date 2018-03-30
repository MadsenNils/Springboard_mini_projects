# Springboard_projects

Author: Nils Madsen
email: nmadsenucsb@gmail.com

This is a GitHub repository for submitting Springboard projects for review.

______________________________
## Unit 5.2: JSON exercise

### File:
sliderule_dsi_json_exercise.ipynb

### Prompt:

Using data in file 'data/world_bank_projects.json' and the techniques demonstrated above,

1. Find the 10 countries with most projects
2. Find the top 10 major project themes (using column 'mjtheme_namecode')
3. In 2. above you will notice that some entries have only the code and the name is missing. Create a dataframe with the missing names filled in.

### Answer variables:
Task 1: top10_countries

Task 2: top10_themes

Task 3: json_df_filled

### Overview of approach:

Data Loading and Cleaning: 
- Load JSON into normalized pandas df
- convert relevant columns into numeric form
- replace empty strings, whitespace-only strings, and null-type entries with NaN
- remove duplicate rows

Task 1:
- group by country name, and aggregate by count of unique project ids
- sort in descending order and extract first 10 rows

Task 2:
- group by theme code, and aggregate by count of unique project ids
- sort in descending order and extract first 10 rows

Task3:
- create dict-like df that maps theme codes to theme names, by dropping na values and duplicate rows
- left merge the json_df and the dict_df to fill in missing theme name values

______________________________


