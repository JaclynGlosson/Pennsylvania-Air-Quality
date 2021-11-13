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

AQI and other gasses are interpreted as follows:

![Air Quality measures](https://github.com/JaclynGlosson/Pennsylvania-Air-Quality/blob/0873d530e490c7cccf99086051f1702477887fd2/images/AQI%20Table.PNG)


<b>[US Census:](https://www.census.gov/data/developers/data-sets/popest-popproj/popest.html)<br> </b>
We used 2019 Population Estimates (as 2020 estimates were unavailible), which requires the inputs of census county and state codes retrieved from [census.gov](https://www2.census.gov/geo/docs/reference/codes/files/st42_pa_cou.txt). The request returns a nested list with county name, population, and density.

<b>[Latitudes and Longitudes:](https://data.pa.gov/Government-That-Works/County-Latitude-Longitude-Points-For-Each-County-S/dvjn-d63b)<br> </b>
In order to retrieve all PA county data from OpenWeather, we looped through a list of latitudes and longitudes.

<b>[Census County Codes:](https://www2.census.gov/geo/docs/reference/codes/files/st42_pa_cou.txt)<br> </b>
In order to retrieve all PA county data from census.gov, we looped through a list of census county codes.

View the interactive dashboard ![here](https://public.tableau.com/app/profile/jackie.glosson/viz/AirQualityDashboard_16367630105040/AirQualityDashboard?publish=yes)

<div class='tableauPlaceholder' id='viz1636769984253' style='position: relative'><noscript><a href='#'><img alt='Air Quality Dashboard ' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Ai&#47;AirQualityDashboard_16367630105040&#47;AirQualityDashboard&#47;1_rss.png' style='border: none' /></a></noscript><object class='tableauViz'  style='display:none;'><param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' /> <param name='embed_code_version' value='3' /> <param name='site_root' value='' /><param name='name' value='AirQualityDashboard_16367630105040&#47;AirQualityDashboard' /><param name='tabs' value='no' /><param name='toolbar' value='yes' /><param name='static_image' value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Ai&#47;AirQualityDashboard_16367630105040&#47;AirQualityDashboard&#47;1.png' /> <param name='animate_transition' value='yes' /><param name='display_static_image' value='yes' /><param name='display_spinner' value='yes' /><param name='display_overlay' value='yes' /><param name='display_count' value='yes' /><param name='language' value='en-US' /><param name='filter' value='publish=yes' /></object></div> 
