# Eat Safe, Love Project

## Table of Contents

1. [Overview](#overview)
2. [Project Details](#project-details)
   - [Goals](#goals)
   - [Methodology](#methodology)
3. [Conclusions](#conclusions)
4. [Future Work](#future-work)
5. [References](#references)

## Overview

The goal of this project is to analyze restaurant ratings data to assist food critics and journalists in making informed decisions for future articles in the magazine *Eat Safe, Love*. This involves setting up a NoSQL database, updating the database, and answering specific queries relevant to the magazine's interests.

## Project Details

### Goals
- Set up a NoSQL database and Jupyter notebook environment.
- Update and maintain the database with the latest data.
- Answer specific queries using the database to provide insights for *Eat Safe, Love*.

### Methodology

1. **Data Collection:**
   - Data was retrieved using the UK Food Standards Agency's API and then saved as a JSON file, which was subsequently imported into a MongoDB database. The dataset includes information such as business name, address, contact details, ratings, longitude/latitude, and scores for management confidence and hygiene.

2. **Data Cleaning:**
   - The data was cleaned using Pandas:
     - A new document was created and inserted into the collection for a restaurant.
     - The `BusinessTypeID` of a restaurant was updated.
     - Documents with "Dover" as the `LocalAuthorityName` were deleted.
     - Longitude and latitude fields were converted from strings to decimal data types.
     - Ratings outside the 1-5 range were set to `null`, and valid 1-5 ratings were converted from strings to integers.

3. **Exploratory Data Analysis (EDA):**
   Queries were performed using Pandas to answer the following questions and create relevant dataframes:
   - Which establishments have a hygiene score equal to 20?
   - Which establishments in London have a `RatingValue` greater than or equal to 4?
   - What are the top 5 establishments with a `RatingValue` of 5, sorted by lowest hygiene score, nearest to the newly added restaurant ("Penang Flavours")?
   - How many establishments in each Local Authority area have a hygiene score of 0?

4. **Tools and Libraries:**
    - `MongoClient` from the `pymongo` library was used to create and manage the database.
    - Pandas was utilized for data manipulation and analysis.
    - `pprint` was used for formatting and displaying query results.

#### Figure 1: Establishments with a Hygiene Score of 20
![Figure 1](https://github.com/pixare7/nosql-project/blob/main/images/fig1.png)

*This dataframe displays establishments with a hygiene score of 20.*

#### Figure 2: London Establishments with a RatingValue ≥ 4
![Figure 2](https://github.com/pixare7/nosql-project/blob/main/images/fig2.png)

*This dataframe shows establishments in London with a `RatingValue` greater than or equal to 4.*

#### Figure 3: Top 5 Establishments Near "Penang Flavours" with a RatingValue of 5
![Figure 3](https://github.com/pixare7/nosql-project/blob/main/images/fig3.png)

*This dataframe highlights the top 5 establishments with a `RatingValue` of 5, sorted by lowest hygiene score, nearest to the new restaurant "Penang Flavours".*

#### Figure 4: Establishments with a Hygiene Score of 0 by Local Authority Area
![Figure 4](https://github.com/pixare7/nosql-project/blob/main/images/fig4.png)

*This dataframe displays the number of establishments in each Local Authority area with a hygiene score of 0.*

## Conclusions

This project provided key insights into restaurant hygiene and rating data, which can inform future content for *Eat Safe, Love*. Notably, it identified establishments with extreme hygiene scores and high ratings in specific areas, helping prioritize potential review targets. 

## Future Work

Future work will include additional data cleaning, such as removing unused columns and mapping IDs to more descriptive names, like converting `BusinessTypeID` to the actual business type name. Additionally, further analysis will explore relationships between variables to uncover deeper patterns, such as those seen in the queries regarding hygiene scores, rating values, and geographical distribution.

## References

[UK Food Standards Agency (2022)](https://www.food.gov.uk/)
. UK food hygiene rating data API. [https://ratings.food.gov.uk/open-data/en-GB](https://ratings.food.gov.uk/open-data/en-GB). Contains public sector information licensed under the Open Government Licence v3.0. Accessed on Sept 9, 2022, and Sept 12, 2022, with the establishment settings as follows: longitude = 51.5072, latitude = -0.1276, maxdistancelimit = 4567, pagesize = 10000, sortoptionkey = distance, pagenumber = (1, 2, 3, 4, 5, 6, 7, 8).

