`Data_visu.ipynb` 

## Title:

The Beer Trip Agency (BTA). 

## Abstract:

Been a rough few weeks, correcting 100 ADA stories. How will you celebrate? A few drinks? A holiday maybe? Why not both :-)  Welcome to BTA (Beer Trip Agency SA), where we design beer-tasting trips around the world taking into account our customers' preferences!
Using the provided data, we design several trips around the world, taking into account different parameters that might be relevant to our drunk-driven clients. We pick the best spots corresponding to characteristics such as alcohol percentage, top-rated beers, and brewery diversity among other things. Then, we establish a general ranking designed in relation to customer preferences, giving more or less weight to the initial ratings. Once our algorithm brews through, we determine the regions that will make up the world tour. We'll propose brewery visits in countries, along with the contacts of the region's best beer lovers/experts. Ale the best for a trip Lager than life!

## Questions to answer:

What's the perfect beer trip depending on your preferences? If you were to plan a beer world tour with your friends,
what would the common ground be? Where is the El Dorado?


## Additional datasets:

- Loaded new dataset about the location superficies (to compute some densities) imported from Wikipedia. Three different dataset have been imported and then merged (countries of the world, countries in the UK and states of the USA) to be consistent with the location given in the description of the beer/breweries. 

- Dataset about the population in each location (once again to compute some densities) imported from Wikipedia (not imported yet).

### Methods: 

### 1) Data preprocessing:

- Importing the additional datasets and cleaning them.
- Matched data sets loading, cleaning and exploration.
- Rate Beer data sets loading, cleaning and exploration.
- Beer Advocate data sets loading, cleaning and exploration.
 
### 2) Building the trip rankings for every preferences: 

- **The percentage of alcohol** (2 rankings, softest and strongest beers). For this ranking, we considered the average percentage of alcohol in beers for every locations. This ranking allows us to find the countries/locations with the strongest/softest beers. Whether you like strong or soft beers this ranking will satisfy any tastes. 
Status : Done

- **The overall ratings of the beers** (2 rankings: the best and the worst). In this ranking, we group ALL the beers per location. We then drop locations with less than 5 beers (we don't want to organise a trip to taste only one or two beer, even if their ratings are great) and compute the average rating of every beers for each locations. Finally, we get two rankings: best rated beers and worst rated beer.
Status : Done

- **The breweries diversity**. The idea about this trip is to sum the amount of breweries per location and then divide by the total area of the region imported from Wikipedia which gives us the number of breweries per km^2. This allows us to propose a tour where we maximize the number of breweries visit while minimizing the number of locations for our customers. 
Status : Done

- **The connoisseur tour** (based on the reviews/ratings of the top reviewers). This world tour aims to propose the best beer trip for the real beer passionate. We want to guarantee that only the best beers will be proposed, which can be done by finding the most active reviewers (thus the most experienced) per site and analyse the ratings to build the ranking.
Status : Incoming (problem to load the .txt file with the ratings in order to match the user_id to the beer_id)

- **The relative amount of reviewers per location's population**. We thought about importing new data from Wikipedia, about the population in the different locations. It could be used to divide the amount of the users from a certain region by the total population to see which location have the biggest proportion of users. This would allow us to propose some destinations where customers would find fellow beer lovers. 
Status : Incoming

- **The countries with the most emerging beer**

Status : Not done yet, still in conception

- **Ranking relatively to certain features from the ratings** (aroma, palate, flavour, ...) 

Status : Not done yet, still in conception


This list is not exhaustive, it shows only the idea we thought about yet, but it's possible that other classifications will be added, or that some of the previous ones will be deleted.

### 3) Computing the overall ranking: 

Visualization of the trip on a map. 
With weights given by customers preferences, we create a personal ranking. 
All the previous rankings will receive points (10pts for 1st, 1pts for the 10th) which will be multiplied by their respective weights and summed for each location. Finally, we can find the location with the most points (El Dorado) and the following ones to build the beer world tour. 

### 4) Complementary informations about the trip:

When the trip is designed, we will organise visits in the best breweries for each location and propose a local guide to show our customers around and give his beer expertise. To give the best experience possible, the local guide is chosen among the most active and involved users of RateBeer or BeerAdvocate. 

## Proposed timeline: 

For milestone P3, we will work on the couple of other features mentioned above which, for the moste part, require to load the .txt file. It is also possible that we will implement new classements if new ideas come to us. We will also find good way to visualize every rankings (for instance using the world map plot that we used). Finally, we will work on complementary informations about the trip (visits, local guide, ...).

## Organization within the team: 

Four of the five members are working on the design of the rankings (each person works on one features) and the fifth member is working on the logistic part (determine the direction the project will take, comments of the code, structure of the notebook, readme writting) :

## Additional question for the TA: 


## Important package to include:

pandas, numpy, matplotlib.pyplot, seaborn, bs4, requests, stats.models.stats, scipy, plotly, us, json
