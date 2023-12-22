## Link to the website


## Guide to run the code

The data files are ordered as follows:
    project_root/
project_root/
|-- README.md
|-- matched_beer_data/
| |-- beers.csv
| |-- breweries.csv
| |-- users.csv
| |-- ratings.csv
| |-- users_approx.csv
|-- RateBeer/
| |-- beers.csv
| |-- breweries.csv
| |-- ratings.txt
| |-- users.csv
| |-- ratings_TTRB.csv
|-- BeerAdvocate/
| |-- beers.csv
| |-- breweries.csv
| |-- users.csv
| |-- ratings.txt
| |-- ratings_TTBA.csv
| |-- preprocess_ratings.ipynb
|-- Data_visu.ipynb
|-- milestoneP3.ipynb

 - Note that ratings_TTRB.csv and ratings_TTBA.csv are file created from the two ratings.txt files respectively from RateBeer and BeerAdvocate. We create these two files  by preprocessing them in the `preprocess_ratings.ipynb` files. Thus, it is important to run `preprocess_ratings.ipynb` before `Data_visu.ipynb` and `milestoneP3.ipynb`. (Note that the preprocessing of the two files takes approximately 4 hours).
 - The external Datasets we are talking aobut in **Step 1** are directly downloaded in the 'milestoneP3.ipynb' notebook from these websites: [USA_states_area](https://en.wikipedia.org/wiki/List_of_U.S._states_and_territories_by_area), [Countries_area](https://en.wikipedia.org/wiki/List_of_countries_and_dependencies_by_area), [population](https://en.wikipedia.org/wiki/List_of_countries_and_dependencies_by_population), [population_usa](https://simple.wikipedia.org/wiki/List_of_U.S._states_by_population) and two small handmade datasets with respectively the populations and area of every countries of the UK.
 - `Data_visu.ipynb` file contains several different way to visualize our different dataset which helped us design the trips mentioned in **Step 4** but also contains all the ranking visualization from trips we did not consider relevant for customers or the ones that we had imagined but that the available dataset did not allows us to realize. 
 - `milestoneP3.ipynb` contains the code for milestoneP3. Some of the cells still display warnings while running. however, this don't cause any issue for executing the notebook. 
 - Note that not every cells of the `milestoneP3.ipynb` notebook put on github has been previously run (the full prerin `milestoneP3.ipynb` was too heavy for github).

### Title:

The Beer Trip Agency (BTA). 

### Abstract:

Been a rough few weeks, correcting 100 ADA stories. How will you celebrate? A few drinks? A holiday maybe? Why not both :-)  Welcome to BTA (Beer Trip Agency SA), where we design beer-tasting trips around the world taking into account our customers' preferences!
Using the provided data, we design several trips around the world, taking into account different parameters that might be relevant to our drunk-driven clients. We pick the best spots corresponding to characteristics such as alcohol percentage, top-rated beers, and brewery diversity among other things. Then, we establish a general ranking designed in relation to customer preferences, giving more or less weight to the initial ratings. Once our algorithm brews through, we determine the regions that will make up the world tour. We'll propose brewery visits in countries, along with the contacts of the region's best beer lovers/experts. Ale the best for a trip Lager than life!

### Research questions:

What would be the perfect beer trip depending on personal's preferences? If you were to plan a beer world tour with your friends,
what would the common ground be? Where is the El Dorado?


### Additional datasets:

- We loaded new datasets about the location superficies (to compute some densities) imported from Wikipedia. Three different dataset have been imported and then merged (countries superficie of the world: [Countries_area](https://en.wikipedia.org/wiki/List_of_countries_and_dependencies_by_area), countries superficie from the UKand states of the USA: [USA_states_area](https://en.wikipedia.org/wiki/List_of_U.S_states_and_territories_by_area) and and a small handmade dataset with the superficie of every countries of the UK to be consistent with the location given in the description of the beer/breweries. 

- In order to compute population densities, we had to load three more datasets about the population in each location: [population](https://en.wikipedia.org/wiki/List_of_countries_and_dependencies_by_population), [population_usa](https://simple.wikipedia.org/wiki/List_of_U.S._states_by_population) and a small handmade dataset with the population of every countries of the UK to be consistent with the location given in the description of the beer/breweries.

### Methods: 

### 1) Data preprocessing:

**Step 1:** Import the several additional datasets, clean them and extract their features that will be useful for our future analysis. While preprocessing these datasets we had to change some of their features to make them consistant with our different beer datasets. For intance the names of the location weren't written in the same manner between the different dataset beer and additional datasets.

**Step 2:** We had three types of dataset at our disposition: data extracted from two of the biggest rating beer website: Beer Advocate and RateBeer and an already merged version of these data that we will call matched data. Each of these dataset contains subdataset with different informaion about the beers, breweries, users, ratings. We imported every files form from BeerAdvocate, RateBeer and the matched ones, clean them and merged them with the additionals datasets from **Step 2:**. We then merging and cleaned the different imported dateset.  

**Step 3**: Explore our different datasets available. This step has several purposes: 
 - To ensure the relevancy of comparing dataset from two different beer rating site (for instance, in `milestoneP3.ipynb` we displayed the different plot and test made to compare the distribution of zscore between the two sites).
 - To test the limits of our dataset to see if our previously though trips are still relevant with the available dataset.
 - To possibly give us new ideas about possible rankings that are both possible to do with our data and interesting for customers.
 
### 2) Building the trip rankings for every preferences: 

**Step 4:** In this part, we tried to build several trips that we thought to be relevant, and tried to use as many features as possible from our different datasets, while keeping in mind that the trip should be enjoyable or interesting for our potential customers.

**Here is a list of all the trip we designed:**

- **The percentage of alcohol** (2 rankings, softest and strongest beers). For this ranking, we considered the average percentage of alcohol in beers for every locations. This ranking allows us to find the countries/locations with the strongest/softest beers. Whether you like strong or soft beers this ranking will satisfy any tastes. 

- **The overall ratings of the beers** (2 rankings: the best and the worst). In this ranking, we group ALL the beers per location. We then drop locations with less than 5 beers (we don't want to organise a trip to taste only one or two beer, even if their ratings are great) and compute the average rating of every beers for each locations. Finally, we get two rankings: best rated beers and worst rated beer.

- **The breweries diversity**. The idea about this trip is to sum the amount of breweries per location and then divide by the total area of the region imported from Wikipedia which gives us the number of breweries per km^2. This allows us to propose a tour where we maximize the number of breweries visit while minimizing the number of locations for our customers. 

- **The connoisseur tour** (based on the reviews/ratings of the top reviewers). This world tour aims to propose the best beer trip for the real beer passionate. We want to guarantee that only the best beers will be proposed, which can be done by finding the most active reviewers (thus the most experienced) per site and analyse the ratings to build the ranking.

- **The relative amount of reviewers per location's population**. We thought about importing new data from Wikipedia, about the population in the different locations. It could be used to divide the amount of the users from a certain region by the total population to see which location have the biggest proportion of users. This would allow us to propose some destinations where customers would find fellow beer lovers. 


For the construction of each of these rankings, with exception of **The connoisseur tour**, we decided to used the files from matched data. After analyzing the proportions of beer that are present in both site versus the ones that are present only in Beer Advocate or Rate Beer, we concluded that we would'nt "loose" too much beer data taking into account only the matched files (Both sites share approximately 90% of beer names). A lot ouf our different trips were build using, among others, the feature "zscore". While analysing the distribution of the zscore between the two sites in **Step 3**, we observed that  BeerAdvocate tend to give higher zscore than Rate Beer. 
We also obsereved that BeerAdvocate had more total reviews than Rate Beer. For these differences to not skew our rankings results, we decided to balance the zscore of every beers by its number of review from both sites. This way, we are sure that the zscore of a beer is not biased by the number of reviews it has on each site.

For the **The connoisseur tour**, we decided to use the files from Beer Advocate and Rate Beer because we wanted to be sure to propose only the best beers to our customers. Thus, we decided to use the ratings of the top reviewers from each site to build the ranking. Indeed, we assume that people who review a lot have relevant opinions because they have experience in the field of beer tasting, even if they review only on one website and not on both. We also decided not to include more than two different locations inside the United States of America on our trip because we thought that it would be more interesting for our customers to visit beer from around the world rather than only from the USA.

### 3) Computing the overall ranking: 

**Step 5:** While trying to build the different trips, we also tried to find a way to visualize the different destinations of every trip. To do so, we used plotly python library to plot the different locations on an interactive world map. We found this library perfectly suitted for our data analysis because it allowed us show both the locations of every country of the trip and their position in the ranking (the size of the circle on the interactive map depends on the location's ranking). We also used the plotly library to help us for visualizations included in the `Data_vizu.ipynb` notebook. Note that the interactive world map are included canot be visualized on github, but can be visualized directly by opening the `milestoneP3.ipynb` and `Data_vizu.ipynb`notebook.

**Step 6:** In order to give customer a way to customize their trip, we decided to create a personal ranking. The idea is to give weights to the different rankings we created in the previous step. The weights are given by the customer depending on his preferences. All the previous rankings will receive points (10pts for 1st, 1pts for the 10th) which will be multiplied by their respective weights and summed for each location. Finally, we use this new personalized ranking them to propose our customer a perfect final beer world tour according to his personal preference.

### 4) Complementary informations about the trip:

**Step 7:** Once the customers has designed his perfect trip, we will arrange visits of the best breweries at each locations and, for each ones, we will provide a local guide to assist customers in exploring the different places and give them his beer expertise. To give the best experience possible, every local guide is chosen among the most active and involved users of RateBeer or BeerAdvocate from each destination of the trip.

**Step 8:** After assigning a local guide to each locations, we will also provide our customers a list of the top breweries to visit for each of the trips destination. This list is made by taking the mean of the zscore of every beers from each brewery. 

## Organization within the team: 

 - Niko Pindao: Explorations of the data, Data visualization for possible trips, Final text for data story.
 - Max Carvalho: Explorations of the data, Interactive Map visualization, Web interface, Data visualization for possible trips, Final text for data story
 - Nicolas Vuillod: Explorations of the data, Data visualization for possible trips, Web interface, overall_ranking, guide finding, Final text for data story.
 - Mae Rollin: Explorations of the data, Web interface, Final text for data story.
 - Luan Dinarica: Explorations of the data, Data visualization for possible trips, Final text for data story.

## Important package to include:

pandas, numpy, matplotlib.pyplot, seaborn, bs4, requests, stats.models.stats, scipy, plotly, us, json, gopy,scipy.stats, statsmodels.api, pylab, datetime

