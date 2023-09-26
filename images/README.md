# Final-Project-Statistical-Modelling-with-Python

## Project/Goals
              
######    We are working with Python to Create Statistical Model and finding potential Relation between different features in our Data.

---> Project is starting with gathering data from different sources using differenet APIs(More detail in process).

---> Joining collected Data and create a Database in Sqlite.

---> Create Tables for the data in Database and get a final result Data with all the tables for further analysis.

---> Performing EDA :
                    Visualizing Data to Identify any outliers and checking Distributions  
                    Data Cleaning 
                    Grouping and Filtering Data
                    Performing Hypothesis to check significance between different features

---> Create  Statistical Model:
                    Creating Model to check for correlations and for prediction between dependent variable and different independent variables.



## Process
### (1) Connecting to CityBikes API:
----> For this part, we will work CityBikes API: [CityBikes](https://citybik.es/) 

    Citybikes is an API that provides bike sharing data for apps, research and projects.
    CityBikes supports more than 400 cities and the Citybikes API is an interesting dataset for building bike-sharing transportation projects.


1. Explore the structure of the API, query the API and understand the data returned. 
2. Choose a city covered by the CityBikes API and retrieve all available bike stations in that city. 
3. For each bike station, use the API to call the latitude, longitude and number of bikes. 
4. Parse the JSON object into a Pandas dataframe.                             



##### Reference Code : https://github.com/pchaudhary12/Statistical-Modelling-with-Python/blob/main/notebooks/city_bikes.ipynb


### (2) Connecting to Foursquare and Yelp APIs
----->
1. Connect to the  [Foursquare](https://developer.foursquare.com/places) API
2. Connect to the [Yelp](https://www.yelp.com/developers/documentation/v3/get_started) API. This API offers similar services as Foursquare.
3. For each of the bike stations in Part 1, query both APIs to retrieve information for the following in that location:
 - Restaurants or bars
 - Various POIs (points of interest) of your choice
4. Create a DataFrame for the Yelp results and Foursquare results. 
5. Compare the quality of the Yelp and Foursquare API. For your location, which API gives you the most complete information/better coverage?

#### Reference Code : https://github.com/pchaudhary12/Statistical-Modelling-with-Python/blob/main/notebooks/yelp_foursquare_EDA.ipynb

## (3) Joining Data

1. Join the data from Part 1 with the data from Part 2 to create a new dataframe. 
2. Use data visualization to explore the data. 
3. Create your own SQLite database and store the data you've collected on the POIs

#### Reference Code : https://github.com/pchaudhary12/Statistical-Modelling-with-Python/blob/main/notebooks/joining_data.ipynb

## (4) Building a Model

1. Build a regression model using Python’s `statsmodels` module that demonstrates a relationship between the number of bikes in a particular location and the characteristics of the POIs in that location.  
2. Interpret results. Expand on the model output, and derive insights from your model.

#### Reference Code : https://github.com/pchaudhary12/Statistical-Modelling-with-Python/blob/main/notebooks/model_building.ipynb


## Results

---> Created a Linear Regression Model between 'Bikes Available' (dependent variable) and ['Distance', 'Rating'] (independent variables)

![Alt text](result.png)


#### Interpretation of the model
(1) Model Fit: Adj. R-squared is very low, i.e it only (1.5)% of variance in Bikes Available is explained by the independent variable

(2) if we remove rating from independent variable and fit the model it shows that the distance doesn't explaind the variance of bikes available at all.

(3) 1.5% variance is for rating only : it does have effect on Bikes Avaialble(but very little)

(4) we can conclude that ther model is very poor and we will need more data to further check relations between variables



#### Removing Rating and recreating model with 'Bikes Available'(dependent variable) and 'Distance' Independent variable

![Alt text](<Screenshot 2023-09-25 203611.png>)


#### Even after removing Rating(indepedent variable), there is no effect of distance on Bikes Available for each Sations

## Challenges 

---> Gathering Data from differenet APIs:
                        Different APIs option available to gather data from:
                                (1) Foursquare:
                                            (1) Need to provide precise parameters for POI(points of interest)
                                            (2) Data mixed with null values
                                            (3) Can make multiple  requests
                                 (2)Yelp:
                                            (1) Detailed response with just including interested point in query
                                            (2) More precise data with no nulls or duplicated values
                                            (3) Very Limited API requests (Have to write complete code as to not run out of request)

---> It is Difficult to chose from data available from different sources:

                            We Worked with Data Available from Foursquare API, as Yelp has Limited API Requests available and it is time consuming to wait for requests to reset and use it           
                                
 


## Future Goals

![Alt text](<More time.png>)