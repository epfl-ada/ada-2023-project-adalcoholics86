# ada-2023-project-adalcoholics86
ada-2023-project-adalcoholics86 created by GitHub Classroom


### Title:

The beer trip agency. 

### Questions to answer:
What is the perfect trip depending on your beer preferences? Is there a common ground for a group of people that don't share the same opinion about beer? If yes, where is the El Dorado?

### Abstract:

We are BTA (beer trip agency) and we design beer tasting trips around the world taking into account our customers' preferences!
To go into a bit more detail, with data from both sites, we're designing several trips around the world taking into account different parameters that might be relevant to our customers (% alcohol, top-rated beers, brewery diversity, ...). First, we'll rank the best places for each of these characteristics. Then, with all these rankings, we'll establish a general ranking that can be designed in relation to customer preferences, giving more or less weight to the initial rankings. Finally, once we've determined the regions that will make up the world tour, we'll propose brewery visits (the best) in each of them, along with the contacts of the region's best beer lovers/experts (the site's users).

### Additional datasets:

- Dataset about the superficies of the location (in order to compute some densities)
# (not imported yet)
- Dataset about the population in each location (also to compute some densities) 

### Methods: 

1) Data preprocessing:

# more details on the preprocessing !!!!
- Importing the additional datasets and cleaning them.
- Merging the initial datasets and cleaning them to keep only the used parameters. 
 
# Determine the amount of trips !!!!
2) Building the trips for every preferences: 
- The percentage of alcohol (2 rankings: softest and strongest beers)
- The overall ratings of the beers (2 rankings: the best and the worst) 
- The breweries diversity

(more to come)

3) Computing the overall ranking: 
With the weights given by customers preferences, we create the ranking that fits the most. 
All previous rankings receive points (10pts for 1st, 1pts for the 10th), then we multiply those rankings with their respective weights and we sum the points for each location from all the ranking. Finally we can find the location with the most points (El Dorado) and the following ones to build the world trip. 

4) Complementary informations about the trip:
When the trip is designed, we organise some visits for the customers (in the best breweries in each location) and we find a local guide that can give them advices on the location (in the users from the location)

### Proposed timeline: 
In this milestone P2, we were more focus about finding some interessant rankings for our customers. We finish some of them (ratings, breweries/km^2, percentage of alcohol), but we are still working on couple of other features for milestone P3
##### Not sur that it is what we have to say here....!!!!

### Organization within the team: 

Four of the five members are working on the design of the rankings (each person works on one features) and the fifth member is working on the logistic part (determine the direction the project will take, comments of the code, structure of the notebook, readme writting). 

### Additional question for the TA: 

