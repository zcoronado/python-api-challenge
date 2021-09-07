# Python API Homework - What's the Weather Like?

## Background

Whether financial, political, or social -- data's true power lies in its ability to answer questions definitively. Taking what I've learned about Python requests, APIs, and JSON traversals to answer a fundamental question: "What's the weather like as we approach the equator?"


## Part I - WeatherPy

In this example, I created a Python script to visualize the weather of 500+ cities across the world of varying distance from the equator. To accomplish this, I utilized a [simple Python library](https://pypi.python.org/pypi/citipy), the [OpenWeatherMap API](https://openweathermap.org/api), and a little common sense to create a representative model of weather across world cities.

The first was to create a series of scatter plots to showcase the following relationships:

* Temperature (F) vs. Latitude: 
 <br>This code is analizing how hot the temperature gets along all latitudes of the selected cities. We can see that the hottest temperatures happen between -20 and 40 latitude which would include the contries of Africa and Europe.</br>


* Humidity (%) vs. Latitude: 
  <br>This code is analizing how humid gets along all latitudes of the selected cities. We do not see a real relationship represented here.</br>

* Cloudiness (%) vs. Latitude:
  <br> This code is analizing how cloudy it gets along all latitudes of the selected cities. We do not see a real relationship represented here. </br>

* Wind Speed (mph) vs. Latitude: 
  <br> This code is analizing how windy it gets along all latitudes of the selected cities. We see that wind speeds tend to stay under 40mph along all latitudes. </br>

Secondly, I ran a linear regression on each relationship. This time, I separate the plots into Northern Hemisphere (greater than or equal to 0 degrees latitude) and Southern Hemisphere (less than 0 degrees latitude):

* Northern Hemisphere - Temperature (F) vs. Latitude: 
  <br> This plot is analyzing the relationship between a city's temperature and latitude where the city is within the Norther Hemisphere. Here we see temperatures are lower in cities where the latitude is higher. This information implies that the further away from the equator a city is, the colder it will be. Our r value confirms this.</br>

* Southern Hemisphere - Temperature (F) vs. Latitude: 
  <br> This plot is analyzing the relationship between a city's temperature and latitude where the city is within the Southern Hemisphere. Here we see temperatures are higher in cities where the latitude is lower. This information implies that the closer from the equator a city is, the warmer it will be. Our r value confirms this.</br>

* Northern Hemisphere - Humidity (%) vs. Latitude: 
  <br> This plot is analyzing the relationship between a city's humidity and latitude where the city is within the Northern Hemisphere. Here, we do not see a relationtion between humidity and latitude. Our r value confirms this.  </br>

* Southern Hemisphere - Humidity (%) vs. Latitude: 
  <br> This plot is analyzing the relationship between a city's humidity and latitude where the city is within the Southern Hemisphere. Here, we do not see a relationtion between humidity and latitude. Our r value confirms this. </br>

* Northern Hemisphere - Cloudiness (%) vs. Latitude: 
  <br> This plot is analyzing the relationship between a city's cloudiness and latitude where the city is within the Northern Hemisphere. Here, we do not see a relationtion between cloudiness and latitude. Our r value confirms this. </br>

* Southern Hemisphere - Cloudiness (%) vs. Latitude: 
  <br> This plot is analyzing the relationship between a city's cloudiness and latitude where the city is within the Southern Hemisphere. Here, we do not see a relationtion between cloudiness and latitude. Our r value confirms this. </br>

* Northern Hemisphere - Wind Speed (mph) vs. Latitude: 
  <br> This plot is analyzing the relationship between a city's windspeed and latitude where the city is within the Northern Hemisphere. Here, we do not see a relationtion between cloudiness and latitude. Our r value confirms this. </br>

* Southern Hemisphere - Wind Speed (mph) vs. Latitude: 
  <br> This plot is analyzing the relationship between a city's windspeed and latitude where the city is within the Southern Hemisphere. Here, we do not see a relationtion between cloudiness and latitude. Our r value confirms this.</br>



### Part II - VacationPy

Now I used weather data to plan future vacations using jupyter-gmaps and the Google Places API. 

* **Note:** if you having trouble displaying the maps, try running `jupyter nbextension enable --py gmaps` in your environment and retry.

* I narrowed down the DataFrame to find our ideal weather condition. For example:

  * A max temperature lower than 80 degrees but higher than 70.

  * Wind speed less than 10 mph.

  * Zero cloudiness.

Used Google Places API to find the first hotel for each city located within 5000 meters of our coordinates.

Plotted the hotels on top of the humidity heatmap with each pin containing the **Hotel Name**, **City**, and **Country**.
