# Pennsylvania Air Quality
#### Group Members: Allie Schneider & Francis Villamater
The objective of this project was to build a dataset to compare the air quality by population density stratified by Pennsylvania county. To do so, we combined two main data sources using open source APIs: OpenWeather and U.S. Census data. To acquire all the necessary data, we had to loop through several API calls with the inputs corresponding to each county in PA (i.e., latitude/longitude and U.S. government specific county codes). We also had to aggregate measures of air pollution over the span of a year, as well as calculate a measure of Air Quality Index over population density. The end product resulted in a dataset of 16 variables and 67 observations. 

Final variables were as follows:
- Latitude
- Longitude
- PA County Name
- County Code
- Average AQI Score
- Population Density
- AQI/Population Density
- Carbon monoxide (CO)
- Nitrogen monoxide (NO)
- Nitrogen dioxide (NO2)
- Ozone (O3)
- Sulphur dioxide (SO2)
- Ammonia (NH3)
- Particulates (PM2.5 and PM10)

### Data Sources
<b>[OpenWeather:](https://openweathermap.org/api/air-pollution)<br> </b>
We used the "Historical Air Pollution" data, which requires the inputs of latitude, longitude, start date (in unix time), and end date (in unix time). Data for air quality was taken from November 27 2020 to October 31 2021. Measures of air pollution were aggregated in order to arrive at an average air pollution measure for each PA county. The request returns a dictionary with data regarding overall Air Quality Index, as well as data about other polluting gasses, including:
- Carbon monoxide (CO)
- Nitrogen monoxide (NO)
- Nitrogen dioxide (NO2)
- Ozone (O3)
- Sulphur dioxide (SO2)
- Ammonia (NH3)
- Particulates (PM2.5 and PM10)
