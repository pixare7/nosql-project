# Eat Safe, Love Project

## Table of Contents

1. [Overview](#overview)
2. [Project Details](#project-details)
   - [Goals](#goals)
   - [Methodology](#methodology)
3. [Conclusions](#conclusions)
4. [Future Work](#future-work)

## Overview

The purpose of this project is to evaluate ratings data to aid food critics and journalists in the decision-making process for future articles for the magazine Eat Safe, Love.  This includes setting up a database, updating the database, and answering specific questions for Eat Safe, Love.  

## Project Details

### Goals
- Set up NoSQL database and jupyter notebook
- Update the database
- Answer specific questions for Eat Safe, Love using the database

### Methodology
Detail the approach and methods used to achieve the project's goals.

In the "Methodology" section, you would typically describe the specific approaches, techniques, tools, and processes you used to accomplish the project's goals. Here are some examples of what you might include:

1. **Data Collection:**
   - Describe how you gathered the data for your project. This could involve web scraping, APIs, downloading datasets from public repositories, or collecting data manually.
   - **Example:** "Weather data was collected using the OpenWeatherMap API for the years 2018-2022, covering various cities across the globe."

   - A .json file containing the restaurant data was imported to create a database in MongoDB.  This included, but was not limited to, business name, address, contact information, rating, longitute/latitude, confidence in management and hygiene scores.  

2. **Data Cleaning:**
   - Explain how you processed and cleaned the data to make it suitable for analysis. This could involve handling missing values, removing duplicates, or correcting data types.
   - **Example:** "Data was cleaned using Pandas, with missing values imputed using the median for continuous variables and mode for categorical variables."
   - a document for a restaurant was created and inserted into the collection
   - the BusinessTypeID of a restaurant was updated
   - documents with "Dover" as the LocalAuthorityName were deleted
   - longitude and latitude were changed from string to decimal data types
   - non 1-5 rating values were changed to Null and numerical 1-5 rating values were changed from strings to integers

3. **Exploratory Data Analysis (EDA):**
   - Outline the steps you took to explore the data, including any visualizations, summary statistics, or correlation analyses.
   - **Example:** "EDA was performed using Matplotlib and Seaborn to visualize the distribution of temperatures across different latitudes."
   Queries were performed using Pandas to answer the following questions and create dataframes.  
   - Which establishments have a hygiene score equal to 20? 
   - Which establishments in London have a RatingVaue greater than or equal to 4. 
   - What are the top 5 establishments with a RatingVlaue of 5, sorted by lowest hygiene score, nearest to the new restaurant added ("Penang Flavours")? 
   - How many establishments in each Local Authority area have a hygiene score of 0? 

4. **Tools and Libraries:**
    - MongoClient from pymongo was used to create the database to store and manage the data. 
    - Pandas was used for data manipulation and analysis
    - pprint was used for testing and displaying query results

#### Figure 0: [Figure Title]
![Figure 0](path/to/figure0.png)

*Brief description of Figure 0.*

#### Figure 1: [Figure Title]
![Figure 1](path/to/figure1.png)

*Brief description of Figure 1.*

#### Figure 2: [Figure Title]
![Figure 2](path/to/figure2.png)

*Brief description of Figure 2.*

#### Figure 3: [Figure Title]
![Figure 3](path/to/figure3.png)

*Brief description of Figure 3.*

#### Figure 4: [Figure Title]
![Figure 4](path/to/figure4.png)

*Brief description of Figure 4.*

#### Figure 5: [Figure Title]
![Figure 5](path/to/figure5.png)

*Brief description of Figure 5.*

## Conclusions

Summarize the key findings or results of the project.

## Future Work

Discuss any potential extensions, improvements, or follow-up projects that could build on the work done in this project.

