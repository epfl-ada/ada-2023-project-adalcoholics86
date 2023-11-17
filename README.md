# ada-2023-project-adalcoholics86
ada-2023-project-adalcoholics86 created by GitHub Classroom

## Title:

The beer trip agency. 

## Questions to answer:

What is the perfect trip depending on your beer preferences? Is there a common ground for a group of people that don't share the same opinion about beer? If yes, where is the El Dorado?

## Abstract:

We are BTA (Beer Trip Agency SA) and we design beer tasting trips around the world taking into account our customers' preferences!
To go into a bit more detail, with data from both sites, we're designing several trips around the world taking into account different parameters that might be relevant to our customers (% alcohol, top-rated beers, brewery diversity, ...). First, we'll rank the best places for each of these characteristics. Then, with all these rankings, we'll establish a general ranking that can be designed in relation to customer preferences, giving more or less weight to the initial rankings. Finally, once we've determined the regions that will make up the world tour, we'll propose brewery visits (the best) in each of them, along with the contacts of the region's best beer lovers/experts (the site's users).

## Additional datasets:

- Dataset about the superficies of the location (in order to compute some densities) imported from Wikipedia. Three different dataset have been imported and then merged (countries of the world, countries in UK and states of the USA) to be consistent with the location given in the description of the beer/breweries. 

- Dataset about the population in each location (also to compute some densities) imported from Wikipedia (not imported yet)

### Methods: 

### 1) Data preprocessing:

# more details on the preprocessing !!!!
- Importing the additional datasets and cleaning them.
- Merging the initial datasets and cleaning them to keep only the used parameters. 
 
### 2) Building the trips for every preferences: 

- **The percentage of alcohol** (2 rankings, softest and strongest beers). The idea for this ranking is to consider the averaged percentage of alcohol in the beers from every location. This ranking is useful because it gave us the countries with the strongest beer and also the softest ! So this can be used for both customers perferences. 
Status : Done

- **The overall ratings of the beers** (2 rankings: the best and the worst). In this ranking, we group ALL the beers per location. Then, we drop the location with less than 5 beers (we don't want to organise a trip to taste one or two beer, even if their ratings are great) and we compute the average ratings of beers from every locations, then we rank them and we get two ranking (best rated beers and worst rated beer).
Status : Done

- **The breweries diversity**. The idea about this trip is to compute the amount of breweries per location and then divide by the total superficies of the region imported from Wikipedia. The result represents the number of breweries per km^2 and it could be relevant for customers that want to visit many breweries without moving around a lot. 
Status : Done

- **The connoisseur tour** (based on the reviews/ratings of the top reviewers). This world tour aims to propose the best beer trip for the real beer passionate. This can be done by quantifying the reviewer’s activity which will have a better beer rating than a less implicated reviewer. This is what motivated the following data preprocessing which will consist in finding the most active reviewers (the 99% percentile having the most ratings) per site and analyse the ratings to build the ranking

Status : Incoming (problem to load the .txt file with the ratings in order to match the user_id to the beer_id)

- **The amount of reviewers relatively to the population of the location**. We thought about importing new data from Wikipedia, about the population in the different locations. It could be used to divide the amount of the users from a certain region by the total population to see which location have the biggest proportion of users. It could be useful if our customers want to go in place with lots of beer lovers. 

Status : Incoming

- **The countries with the most emerging beer**

Status : Not done yet, still in conception

- **Ranking relatively to certain features from the ratings** (aroma, palate, flavour, ...) 

Status : Not done yet, still in conception


This list is not exhaustive, it shows only the idea we thought about yet, but it's possible that other classifications will be added, or that some of the previous ones will be deleted.

### 3) Computing the overall ranking: 

With the weights given by customers preferences, we create the ranking that fits the most. 
All previous rankings receive points (10pts for 1st, 1pts for the 10th), then we multiply those rankings with their respective weights and we sum the points for each location from all the ranking. Finally we can find the location with the most points (El Dorado) and the following ones to build the world trip. 

### 4) Complementary informations about the trip:

When the trip is designed, we organise some visits for the customers (in the best breweries in each location) and we find a local guide that can give them advices on the location (in the users from the location)

## Proposed timeline: 

In this milestone P2, we were more focus about finding some interessant rankings for our customers. We finishd some of them (ratings, breweries/km^2, percentage of alcohol). For milestone P3 we will firstly work on the couple of other features mentioned above which, for the moste part, require to load the .txt file. It is also possible that we will implement new classements if new ideas come to us. We will also find good way to visualize every rankings (for instance using the world map plot that we used). And finally, we will work on the complementary informations about the trip (visits, local guide, ...).

## Organization within the team: 

Four of the five members are working on the design of the rankings (each person works on one features) and the fifth member is working on the logistic part (determine the direction the project will take, comments of the code, structure of the notebook, readme writting) :

## Additional question for the TA: 


## Important package to include:

pandas, numpy, matplotlib.pyplot, seaborn, bs4, requests, stats.models.stats, scipy, plotly, us, json
