# Microsoft's New Movie Studio

## Overview

This project aims to give advice to Microsoft (hypothetically) on which types of movies to create for their new movie studio based on data from IMDB, TMDB, BOM and TN. The data is provided by Flatiron school and collected from the respective websites. 

Using explatory data analysis, I tried to understand what are some important factors for being successful in the industry.

## Business Problem

The business needs general overview about the movie industry. 
    
I believe deciding on the movie genre and the people to work with for the movie are important factors and is a good starting point for a new movie studio. Given the data, I think ratings and profit are good measures of success for a movie.

If we understand which genres are more profitable and have higher ratings, the business can invest in those kind of movies. 

## Data Understanding

The data is collected from Box Office Mojo, IMDB, Rotten Tomatoes, and TheMovieDB.org. The data has information about movie titles, genres, directors, actors, profits, release year.

The data provides information about 16184 movies when merged on common columns. I have included information about movie genres, profit, primary people such as directors, writers and actors along with ratings.

Target variables are the ratings and profit.


## Methods

### Data Preparation
***
Here are the datasets that I used for analysis:
    
imdb datasets: imdb_title_basics, imdb_title_crew, imdb_title_principals, imdb_title_ratings, imdb_name_basics

tmdb dataset: tmdb_movies

bom dataset: bom_movie_gross

tn dataset: tn_movie_budgets


I dropped the following columns from the data:

        original_title, primary_title, Unnamed: 0, genre_ids, id, nconst, tconst,
        original_language, release_date, start_year, birth_year, death_year, 
        known_for_titles,  category, job, characters, vote_count, 
        runtime_minutes, ordering, primary_profession, directors, numvotes, writers

I created a value 'profit', which is simply the worldwide_gross minus production_cost.
       
I dropped rows with missing worldwide_gross or production_cost values. Dropping the nan values, rather than replacing them is an appropriate choice, since I want to provide accurate information.
        
I later dropped studio, year, domestic_gross, foreign_gross, worldwide_gross columns, since they are not necessary for further analysis.

### Data Modeling

I wanted to understand the profitability of different genres of movies.
I also wanted to analyze the change of ratings for different genres. I checked both imdb and tmdb ratings.
    
Secondly, I wanted to find out whom Microsoft should work with for the best profit. Which directors, writers or actors are deriving the most profitable movies and which of them have the best ratings?
    
I used the domestic_gross and foreign_gross to calculate the profit at my first attempt. Then, I found out the information about production_budget, so I included that in the calculation to get a better result.
    
I think deciding the genres of the movie and whom to work with based on the profit and ratings is a good step for a first attempt at creating a new movie studio. This will give an general sense of the indsutry.


## Evaluation

We have some general knowledge about how to make a profitable and popular movie in terms of genres and directors. I think this is a good first step in analysis.
    
I think these results would generalize beyond this data because there are 16184 movies, which is a quite large number.
    
I think this analysis will be helpful in choosing genres and people to work with.


## Conclusions

In terms of best movie genres for the highest profit, here are the top 5 genres that I would recommend:
        
        1. Adventure,Drama,Sport
        2. Biography,Documentary,History
        3. Sci-Fi
        4. Documentary,Drama,Sport
        5. Adventure,Drama,Sci-Fi
        
![graph1](./images/ProfitByGenres.png)
        
One important note about this list is it gives a combination of genres instead of one. That is how the original data was provided, thus the result is recommending a mix of genres for a new movie. 
        
Also, for the highest profit, the company should consider the top directors to work with for a new movie. Here are the top 5 directors that brought in the highest profit:
        
        1. Adam Green
        2. Chris Buck
        3. Joss Whedon
        4. Anthony Russo
        5. Kyle Balda

![graph1](./images/ProfitByPeople.png)
        
In terms of ratings, IMDB and TMBD had different results on the best genres. 
        
Here are the top 5 movie genres by average votes on TMDB:
        
        1. Documentary,History
        2. Mystery,Thriller
        3. Biography,Drama,Musical
        4. Adventure,Drama,Sci-Fi
        5. Crime,Documentary

![graph1](./images/TMDBratingByGenres.png)

And, here are the top 5 genres according to IMDB ratings:
        
        1. Adventure
        2. Action,Sport
        3. Crime,Documentary
        4. Adventure,Drama,Sci-Fi
        5. Mystery,Thriller

![graph1](./images/IMDBratingByGenres.png)

Again, in terms of ratings, IMDB and TMBD had different results on the best directors to work with. 
        
Here are the top 5 directors by average votes on TMDB:

        1. Tom McCarthy
        2. Sunkanmi Adebayo
        3. Chris Weitz
        4. Ben Evans
        5. J.R. Sawyers

![graph1](./images/TMDBratingByPeople.png)

Here are the top 5 directors by average votes on IMDB:
        
        1. Richard Heap
        2. Ricardo Martinez
        3. Mike Erickson
        4. Shannon Keith
        5. Adam Shaw

![graph1](./images/IMDBratingByPeople.png)

I think there are many other factors to consider, such as the time of the year, the economy or any crisis going on, that are not included in this analysis. Therefore, this primary analysis will give a general idea about where to start, but more analysis should be done for better understanding of the industry.
        
I can focus on specific genres instead of a mix of genres. I can also analyze the writers and actors for a more comprehensive analysis.


## Repository Structure

dsc-phase1-project-template.ipynb is a Jupyter Notebook containing all analysis and visualizations for the project.

DS_Project_Presentation.pdf contains presentation for the project.

Data folder contains zipped data about movies and provided by Flatiron School for the project. Data comes from IMDB, Rotten Tomatoes, and TMDB and Box Office Monjo.

Images folder contains the visualization created for analysis.
```
├── README.md                           <- The top-level README for reviewers of this project
├── dsc-phase1-project-template.ipynb   <- Narrative documentation of analysis in Jupyter notebook
├── DS_Project_Presentation.pdf         <- PDF version of project presentation
├── data                                <- Both sourced externally and generated from code
└── images                              <- Both sourced externally and generated from code
```