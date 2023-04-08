## _Movie Recommender System_

> Check out my detailed description of the project in my Medium story. 
https://medium.com/@karrmanbhatia29/movie-recommender-system-project-1a17c4d55136


![image](https://github.com/Karrmanbhatia/Movie-Recommender-System/blob/main/recommendations.gif)


## Contents of the project
1.	What is a Recommender System?
2.	Types of Recommender Systems
3.	Project Flow
4. 	About the data set and python packages 
5. 	Pre-Processing
6. 	Model Building 
7.	Creating a website 
8. 	Deployment

## Steps Taken
•	Data set will be chosen
•	Building a model on it
•	Convert it into a website
•	deploy it on the server


## What is a Recommender system?
When we go out shopping, what is the flow? Let’s say we are shopping for clothes. Let’s say we wish to buy a pair of jeans; we pick one style and ask the shopkeeper to show us styles similar to what we like. In an offline setting, we can call this a recommender system. The salesman knows the product, and he is recommending a particular product. The machine is a salesman in the online environment who recommends the product according to what we browsed.
Recommender systems are used in various fields nowadays; it is used to suggest a song or a product on an e-commerce website; YouTube, FB, Instagram, and Netflix have recommender system too. 

## Types of Recommender Systems
Two types: - 
1.	Content-based
2.	Collaborative filter-based
Content-Based: -
Recommends based on similarity of the content. If you watch cricket videos on YouTube, you will be recommended only more cricket matches, not songs.  
Collaborative filter-based
Content is filtered based on the user’s interest. Let’s say P1 and P2 have a similar liking of movies. They might be giving an equal rating to the film. So now, when P1 watches a new movie, and since we know that P1 and P2 have the same interests, the new film would also be recommended to person P2. This happens in reels as well. My friend and I like similar reels; the reels my friend watches; will also be recommended to me.  
We will be making a content-based recommender system.

## Project Flow
1.	pre-processing of data
2.	building a Machine learning model
3.	convert the model into a website 
4.	deploy the website

 
## About the data sets and Packages
 
We had two datasets – 
1.	one has data about the movie data. E.g., release date, run time, languages, original languages, etc. 
2.	Second, having movie id, cast, and crew. 
 
 
## Processing of the Data
•	We removed the missing data. Some movies did not have overview dropna(inplace=True)
•	We formatted the data so that strings were converted into a list. And uniformity is maintained in all columns.  
•	We removed the space between the first and last names of people  to create one tag of a person rather than two tags (first name and last name). This concept is applied to all things   in names of directors, cast, and genres (Science Fiction  ScienceFiction). 
•	Using a function, we pick up three prominent cast members of the film and leave out the rest of the info in the form of a dictionary. 
 
 
## Model Building 
After cleaning and setting data in an appropriate format, we must start finding similarities in texts to proceed with our recommender system. 
Text Vectorization: 
Scenario:
We have created tags for movies. The problem Statement is to create a website where the user inputs the film’s name.  And we must show the most similar five films to the user. 
Now, out of 5000, how to know which movie is most similar? We need to find this out based on tags.
Observe the tags of movie one and movie 2. Now how much similar are they? This is dependent on how similar their text is. We need to calculate the similarity score between the two. 
 
We will convert every tag /text of the movie to a vector. Every film is a vector. We will find the closest vectors to recommend a movie.

### Concept:
Converting text to vectors is called Text Vectorization.
The technique used is - Bag of words.
Bag of words: Since we have multiple tags of a movie, we will concatenate all the tags; after concatenation, we get a long string with many words. We will take out the 5000 most common words from that large text. 
We will pick out the top 5000 words of the highest frequency.
M1:	W1	W2	W3
M2	3	5	6
M3	2	4	8
This acts like a vector of the Wn dimension.

## Deploy to Heroku
On heroku free tier we can start two containers using two dynos, but there isn't a way for the containers to communicate with each other on Heroku. So, we push everything.
 
