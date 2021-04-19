# Analyzing the Gender Gap in Hollywood Movies

![alt text](https://ofilispeaks.com/wp-content/uploads/Screen-Shot-2021-04-19-at-5.32.15-PM.png)

# 0.0 Problem Statement

A persons sex and facial features can unfairly determine what type of roles they play in Hollywood Movies, which has a big impact on influencing societal stereotypes. Thus, a classification model will be built to predict a persons role in Hollywood based on their sex, while simultanesouly examining portrayals of sex in popular Hollywood movies and its impact on real-life sexist stereotypes. 

# 1.0 Data Source

1. **Kaggle** IMDb movies extensive dataset, The movies dataset includes 85,855 movies with attributes such as movie description, average rating, number of votes, genre, etc. The ratings dataset includes 85,855 rating details from demographic perspective. The names dataset includes 297,705 cast members with personal attributes such as birth details, death details, height, spouses, children, etc. The title principals dataset includes 835,513 cast members roles in movies with attributes such as IMDb title id, IMDb name id, order of importance in the movie, role, and characters played. https://www.kaggle.com/stefanoleone992/imdb-extensive-dataset


2. **Wikipedia CAST Scraping** Wikipedia API will be used to scrape the CAST roles of Major actors. This is already available in source #1 above, but Wikiepedia gives more casting information for major actors, which I hope to use to supplement my data. https://pypi.org/project/wikipedia/


3. **(Strtetch Goal) Wikipedia Picture Scraping** Wikipedia API will be used to scrape images of popular authors in my DataSet. https://pypi.org/project/wikipedia/

> NOTE: Data has been scraped from the publicly available website https://www.imdb.com. All the movies with more than 100 votes have been scraped as of 01/01/2020.
> 

# 2.0 System Requirements

- Python==3.7.3
- gensim==3.8.1
- nltk==3.4.5
- pandas==0.25.2
- matplotlib==3.1.1
- numpy==1.17.2
- spacy==2.2.1
- beautifulsoup4==4.8.0

# 3.0 Data Dictionary

| Feature                 | Explanation                             | Data Type      |
| ----------------------- | --------------------------------------- | -------------- |
| original\_title         | original movie title                    | String         |
| birth\_name             | cast member birth name                  | String         |
| category                | category of job done by the cast member | String         |
| characters              | name/role of the character played       | Complex String |
| children                | number of children                      | Float          |
| country                 | movie country                           | String         |
| date of birth           | date of birth                           | Date/Time      |
| divorce                 | number of divorces                      | Float          |
| duration                | duration in minutes                     | Float          |
| genre                   | movie genre                             | String         |
| height                  | height (in cm)                          | Float          |
| imdb\_name\_id          | name id on imdb                         | String         |
| imdb\_title\_id         | title ID on IMDb                        | String         |
| metascore               | metascore on a scale of 1 to 100        | float          |
| name                    | cast member name                        | String         |
| ordering                | order of importance in the movie        | Ordinal        |
| original\_title         | original movie title                    | String         |
| production_company      | company that produced movie             | String         |
| sex                     | sex of cast member                      | Binary         |
| title                   | movie title name                        | String         |
| year                    | year of release                         | Integer        |

# 4.0 Preliminary Data Cleaning

### 4.1 Data Cleaning
- Import Kaggle Dataset
- Generate Cast/Roles from each IMDB movie in Wikipedia.

### 4.2  Dataset Merging
- Merge all the created datasets above into one, and filter it down. Final data frame should contain
    - movie character [IMDB and Wikipedia]
    - actor who played character [IMDB and Wikipedia]
    - age of actor at time of movie release [IMDB]
    - role description [IMDB and Wikipedia]
    - name of movie [IMDB and Wikipedia]
    - budget of movie [IMDB and Wikipedia]
    - box office revenue [IMDB and Wikipedia]
    - sex [IMDB]
    - height [IMDB]
    - where movie was produced [IMDB]

# 5.0 Exploratory Data Analysis and Hypothesis

1. Question 1: Are there movie genres that do not exhibit a gender gap?

2. Question 2: Are women receiving more lead movie roles today than in the past?

3. Question 3: How has the fairness of female representation in movies changed over the years?

# 6.0 Predictive Modelling

1. Create Clusters based on roles, to potentially use that to group clusters of roles.
2. Take all the roles and filter based on a set of manual filtering. e.g Receptionist and Secretary, get grouped into one role.
3. Use role description to predict sex.

# 7.0 Observations and Conclusions

![alt text](https://ofilispeaks.com/wp-content/uploads/Screen-Shot-2021-04-19-at-5.32.31-PM.png)
