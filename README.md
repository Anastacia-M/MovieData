# Movies Data Analysis Project
## Table of Contents:
 - [Project Overview](#project-overview)
 - [Data Sources](#data-sources)
 - [Exploratory Data Analysis](#exploratory-data-analysis)
 - [Results](#results-and-findings)
 - [Challenges](#challenges-in-analysis)

### Project Overview
This data analysis project aims to analyze movie performance and trends from 2012 to 2016, identifying patterns, making data-driven recommendations, and enhancing our understanding of the industry's dynamics.

### Data Sources
The primary dataset for this analysis is the [Movies Data_source.xlsx](https://github.com/user-attachments/files/16448651/Movies.Data_source.xlsx) file, which includes comprehensive details on each movie's performance, director, actors, release date, and other relevant information.

### Tools
-	Power query: Used for Data cleaning and preparation
-	Excel, Pivot Tables, and Charts: Utilized for data analysis, report creation, and visualizations.

### Data Cleaning and Preparation
In the initial data preparation and processing phases, I performed the following tasks:

 - Data loading and inspection
 - Handling errors and missing values
 - Data cleaning, formatting, and organizing
 - Transforming the data into the required format, ensuring it was ready for analysis while maintaining data integrity throughout the process

The Excel file, after data cleaning and preparation, with all the Power Query steps, can be downloaded here: [Movies Data_ready for dashboard.xlsx](https://github.com/user-attachments/files/16448628/Movies.Data_ready.for.dashboard.xlsx)
To go through the Power Query steps in this file, please use "Movies Data_source.xlsx" from the Data source section above as the source file.

### Exploratory Data Analysis 
For the purpose of gaining comprehensive insights from the movie industry data between 2012 and 2016, the following questions were asked:
 - Which movies topped the box office revenue charts from 2012 to 2016?
 - Which movies had the highest production budgets during this period?
 - Which actors generated the highest box office revenue?
 - Who is the top director by box office revenue from 2012 to 2016?
 - Which movie had the highest ROI from 2012 to 2016? Which movie had the lowest ROI?
 - Which genre led in box office revenue, indicating a strong audience preference?
 - What are the high-revenue generating genres?
 - How did mid-tier genres like Drama and Action/Comedy perform financially?
 - What trends are observed in niche markets like Sci-Fi and Family genres?
 - Which lower revenue generating genres were still popular, though less dominant?

### Results and Findings
The data from 2012-2016 highlights a clear preference for action-related genres, both standalone and combined with other elements like adventure, comedy, and fantasy. Comedy and drama also perform well, appealing to a broad audience. The considerable revenue from sci-fi and family genres underscores the varied tastes of moviegoers. Overall, the diverse revenue distribution across genres suggests that the film industry benefits from catering to multiple interests and preferences.

As an example, the movie with the highest box office revenue was "Despicable Me 2," which had a box office revenue of $970,800,000, a budget of $76,000,000, and an ROI of 1,177%. Jennifer Lawrence topped the box office revenue list with a total of $2,204,300,000. Chris Renaud leads the list of top directors with a box office revenue of $2,044,500,000.
However, the most profitable movie was "The Devil Inside," which falls in Horror/Drama catogory, with a budget of $1,000,000, a box office revenue of $101,800,000, and an ROI of 10,080%.

The Excel file with dashboard can be downloaded here: [Movies Data_dashboard.xlsx](https://github.com/user-attachments/files/16448600/Movies.Data_dashboard.xlsx)

![Movies Data Dashboard](https://github.com/user-attachments/assets/a28b1bc3-8899-48fe-8d87-1e5cc5d15db1)

### Challenges in Analysis

#### M Language

One of the interesting challenges I encountered was working with a specific code in M language to group genres together for further analysis. The dataset included two columns of genres, and the task was to combine them into a consistent format, such as "action/comedy" instead of "comedy/action". This required careful manipulation of the data to ensure uniformity and accuracy in the genre combinations.

```
= Table.Group(#"Sorted rows", {"Movie Title"}, {{"Combined Genre", each Text.Combine([Concat Genre], " / "), type text},
            {"AllData", each _, 
                type table [Movie Title=nullable text, Release Date=nullable date, Wikipedia URL=nullable text, Concat Genre=nullable text, Director_First_ID=nullable number, Cast_First_ID=nullable number, Cast_Second_ID=nullable number, Cast_Third_ID=nullable number, Cast_Fourth_ID=nullable number, Cast_Fifth_ID=nullable number, #"Budget ($)"=nullable number, #"Box Office Revenue ($)"=nullable number, Director=nullable text, Actor 1=nullable text, Actor 2=nullable text, Actor 3=nullable text, Actor 4=nullable text, Actor 5=nullable text]}})
```
