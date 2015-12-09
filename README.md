
#Is Leonardo DiCaprio going to win an Oscar at last?

![photo](images/photo.png)

[Image credit 1](http://www.tasteofcinema.com/wp-content/uploads/2014/08/best-Leonardo-DiCaprio-movies.jpg) .
[Image credit 2](http://umlconnector.com/wp-content/uploads/AE-Sad-Leo.png)


要求
IPython Process Book

An important part of your project is your iPython process book. Your process book details your steps in developing your solution, including how you collected the data, alternative solutions you tried, describing statistical methods you used, and the insights you got. Equally important to your final results is how you got there! Your process book is the place you describe and document the space of possibilities you explored at each step of your project. We strongly advise you to include many visualizations in your process book.Your process book should include the following topics. Depending on your project type the amount of discussion you devote to each of them will vary:

Overview and Motivation: Provide an overview of the project goals and the motivation for it. Consider that this will be read by people who did not see your project proposal.

Related Work: Anything that inspired you, such as a paper, a web site, or something we discussed in class.

Initial Questions: What questions are you trying to answer? How did these questions evolve over the course of the project? What new questions did you consider in the course of your analysis? - Data: Source, scraping method, cleanup, storage, etc.

Exploratory Data Analysis: What visualizations did you use to look at your data in different ways? What are the different statistical methods you considered? Justify the decisions you made, and show any major changes to your ideas. How did you reach these conclusions?

Final Analysis: What did you learn about the data? How did you answer the questions? How can you justify your answers?

Presentation: Present your final results in a compelling and engaging way using text, visualizations, images, and videos on your project web site.

Describe the storytelling elements and goals in your process notebook and show us sketches and screenshots of different website iterations. As this will be your only chance to describe your project in detail make sure that your process book is a standalone document that fully describes your process and results.

##1  Overview and Motivation

###1.1 Motivation
#Provide an overview of the project goals and the motivation for it. Consider that this will be read by people who did not see your project proposal.

The Academy Awards, more commonly knows as the Oscars, is one of the most anticipated and oldest entertainment annual awards ceremonies in the world. Ever since 1929, the Oscars has honored cinematic achievements (usually) every February for 87 years. Each year, the media and cinema lovers try to predict the winners before the grand ceremony. This year, with two months to go until another exciting Oscars (the 88th), we wish to join the crowd of spectators and make our own predictions on which movie and which actors and actresses will most probably take the golden statue home. 

The Oscars gives out awards in 24 categories, ranging from the most exciting Best Picture, Best Leading Actor/Actress to Best Documentary Short Subject and Best Writing. Our project tries to predict which movies are most likely to win any of the following awards in Best Picture, Directing, Best Actor in a Leading Role, Best Actress in a Leading Role, Best Actress in a Supporting Role and Best Actor in a Supporting Role.

Because Leonardo DiCaprio had been nominated 5 times over the past 10 years, but has never won an Oscar, we take special interest in his award-outcome in the 88th Oscar next year. (He is starred in a movie "The Revenant", which is scheduled to be released on December 25, 2015.)


<table>
<tr>
<th>Year</th>
<th>Leonardo DiCaprio's Oscar Nominations</th>
</tr>
<tr>
<td>2014</td>
<td>Best Performance by an Actor in a Leading Role (
The Wolf of Wall Street (2013))</td>
</tr>
<tr>
<td>2014</td>
<td>Best Motion Picture of the Year (
The Wolf of Wall Street (2013)) </td>
</tr>
<tr>
<td>2007</td>
<td>Best Performance by an Actor in a Leading Role (
Blood Diamond (2006)) </td>
</tr>
<tr>
<td>2005</td>
<td>Best Performance by an Actor in a Leading Role
(The Aviator (2004)) </td>
</tr>
<tr>
<td>1994</td>
<td>Best Actor in a Supporting Role (
What's Eating Gilbert Grape (1993) ) </td>
</tr>
</table>

###1.2 Project Overview and Flow

In order to predict the winners of next year's Oscars, we will collect data on movies, actors and actresses from IMDb, Rotten Tomatoes and Wikipedia. After obtaining the data and constructing the dataset, we will explore the data and train several classification models for our predictions. 

This project will contain:
1. Scraping the web and creating the dataset for the prediction.
2. Exploratory Data Analysis (EDA).
3. Model fitting and training
4. Prediction
5. Conclusion

⧸⧸



##2 Scraping and constructing data frame
Before we start scraping, let's spend some time discussing the data source and the scrapping methods we used.

###2.1 A short discussion on datasource and scraping methods
The scrapping contains two parts, one for all the movies, actors and actresses nominated and won before the 87th Oscars in 2015, the other for all movies that are eligible for nomination in the 88th Oscars (i.e. all movies in 2015, from midnight at the start of 1 January to midnight at the end of 31 December).

**Part 1** For movies released before 2015

We started with a list of all Oscars winners and nominees in our  categories of interest up to 2014. The categories are: Best Picture, Best Directing, Best Actor in a Leading Role (hereafter denoted as Best Leading Actor), Best Actress in a Leading Role (Best Leading Actress), Best Actor in a Supporting Role (Best Supporting Actor) and finally, Best Actress in a Supporting Role (Best Supporting Actress). The list is here: [academy_awards_updated.csv](academy_awards_updated.csv). We took the list of all nominated and winning movies up to 2011 from [here](https://www.aggdata.com/awards/oscar) and manually added updated movies so that the file contains all nominated and winning movies up to 2014.

Using the list of movie titles, we scrape  IMDb using a unofficial their free unofficial public API to gather information on each movie and later about their IMDb and Rotten Tomatoes attributes. We then scraped information we think that might be useful for our predictions about the three leading actors/actresses and the directors of each movie on the list. Some example features are credits, date of birth and award nominations. For details about how we scraped the  data set, please see [r1_scrapingimdb](r1scrapingimdb.ipynb)⧸⧸scrape⧸⧸ later on⧸⧸ each actor and actress on the list
 ⧸⧸[r1_scrapingimdb](r1scrapingimdb.ipynb)⧸⧸[r1_scrapingimdb](r1scrapingimdb.ipynb)⧸⧸⧸⧸

We also scrapped wikipedia for all the nominated movies, then scrapped the budget and box_office information off of wikipedia. For details of this part of scrapping, please see notebooks: [a1_scrape_wiki_movie](a1_scrape_wiki_movie.ipynb), [a2_clean_wiki_movie_df](a2_clean_wiki_movie_df.ipynb), ⧸⧸[a3_clean_wiki_movie_df](a3_clean_wiki_movie_df.ipynb).[a3_clean_wiki_movie_df](a3_clean_wiki_movie_df.ipynb).


**Part 2** For movies released in 2015

We scrapped [wikipedia page](https://en.wikipedia.org/wiki/2015_in_film) for the list of movies released in 2015 up to the date of the scape, which is 4th of December. Because the movies elegible for the Oscar [a3_clean_wiki_movie_df](a3_clean_wiki_movie_df.ipynb).


##3. Exploratory Data Analysis (EDA).
### 3.1 Run Time
First, let us look at the run time of winner and nominee movies, shown in fig 2. The green shows the runtime of the nominees and the red shows the runtime of the winners. We also plot the mean and median of each group. The mean of nominees is 24 minutes less than the mean of the winners. The median of the nominees is 14 minutes less than that of the winners. Though the mean and median are different in each group, we cannot tell if movie runtime is a feature that explicitly divides the winners from the nominees because the distributions are very much overlapped. 

![histogram](images/histogram.png)

### 3.2 Budget and Box-office 
Besides runtime, we think box office and budget might also play roles in winning oscar. The figure below shows the box office and budget of winning and nominee movies respectively. For box-office, the winning movies tend to have a more uniform distribution than all the nominee movies in USD dollars. While for the budget, winning movies have approximately the same distribution as nominee. Therefore, box-office might be a significant feature in the model. However, it can also be that the movie has won a oscar so more people tend to watch that movie. To deal with this issue, we should have only scarped the box office until right before the oscar. Yet due to the time issue, we just simply scraped the box office until now. 

![bo](images/bo.png)

![budget](images/budget.png)

### 3.3 Age and credit of directors and actors
The first one is a comparison of the mean of the actors' age at the time of their nominations for the winners and the nominees. The second to fourth are similar comparisons. We used the same convention of using green for the nominees and red for the winners. The distributions of the two groups overlap, giving us no additional information on how to distinguish between the winners and the nominees. 

![ac](images/ac.png)

### 3.4 Genre 
To do more exploration on the data, we plot the mean credits of actors and directors in each year for each genre of movie. We can see that actors have higher credits than director in general. By looking at the percentage of genre for nominee and winning movies, we can have some general idea of what kind of genre has larger chance of winning. For example, 'Drama' and 'Romance' have high chance of being nominated and winner.

![genre](images/genre.png)

![genre2](images/genre2.png)

### 3.5 Geography and Birthplace
Just for fun, we also plot two world maps to show where are the actors and directors come from. Most of the actors and directors are from America and Europe, which makes sense because most of the movies in our data come from Hollywood. 

![map1](images/map1.png)

![map2](images/map2.png)





    
