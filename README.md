# Health and Proximity to Outdoor Areas in Tennessee

![GitHub last commit](https://img.shields.io/github/last-commit/derekbeistad/health-and-proximity-to-natural-areas-analysis)
![GitHub issues](https://img.shields.io/github/issues-raw/derekbeistad/health-and-proximity-to-natural-areas-analysis)

# Table of Contents
- [Table of Contents](#table-of-contents)
- [Motivation](#motivation)
- [Technologies](#technologies)
- [The Data](#the-data)
- [Methods](#methods)
- [Conclusions](#conclusions)
- [Link to Dashboard](#link-to-dashboard)
- [Resources](#resources)

# Motivation
[(Back to top)](#table-of-contents)
## Does one's proximity to the outdoors affect their overall health?

<details>
<summary><b>Investigate the relationship between living close to parks and someone's health</b></summary>
<br/>
Staying active is a crucial part of a healthy lifestyle. According to the American Heart Assocciation, 150 minutes a week of moderate-intensity activity can  "Lower the risk of heart disease, stroke, type 2 diabetes, (and) high blood pressure..." [1]. With this information, we want to know if living closer (having easy access) to a park will affects someone's overall health.
    
![Tableau screenshot](https://github.com/derekbeistad/health-and-proximity-to-natural-areas-analysis/blob/main/images/intro-img.jpg?raw=true)

</details>


# Technologies
[(Back to top)](#table-of-contents)
- Python
- Tableau
- Pandas
- Numpy
- GeoPandas
- Folium
- Shapely
- MatPlotLib

# The Data
[(Back to top)](#table-of-contents)
## USA Parks
### From ArcGIS - updated 2023 December 27
https://www.arcgis.com/home/item.html?id=578968f975774d3fab79fe56c8c90941
    <details>
    <summary><b>Parks Data Summary</b></summary>
    <br/>
- Gathered the park boundaries for parks, gardens, and forests at national, state, county, regional, and local levels
- 722 natural areas in or bordering Tennessee
![Parks Map screenshot](https://github.com/derekbeistad/health-and-proximity-to-natural-areas-analysis/blob/main/images/parksmap.jpg?raw=true)
![Num of Parks by Type screenshot](https://github.com/derekbeistad/health-and-proximity-to-natural-areas-analysis/blob/main/images/parks-by-type.jpg?raw=true)
    </details>
## Health Data
### From CDC - updated 2023 August 25
https://data.cdc.gov/500-Cities-Places/PLACES-Local-Data-for-Better-Health-Place-Data-202/eav7-hnsx/about_data
    <details>
    <summary><b>Health Data Summary</b></summary>
    <br/>
- Health data for 429 different locations throughout Tennessee for the years 2020 and 2021
- Health data is for adults aged 18 and older.
![Health Data Map screenshot](https://github.com/derekbeistad/health-and-proximity-to-natural-areas-analysis/blob/main/images/healthdata-map.jpg?raw=true)
    </details>

# Methods
[(Back to top)](#table-of-contents)
    <details>
    <summary><b>Health Data Hurdles</b></summary>
    <br/>
Finding a dataset with health data tied to specific geolocations was difficult. I eventually cam across the PLACES dataset from the CDC. This provides data for 36 different measures of health broken down by location. I then decided to focus the research on 8 of the 36 measures

- Stroke
- Obesity
- Asthma
- High Blood Pressure
- Coronary Heart Disease
- Diabetes
- Depression
- Lack of Health Insurance
    
    </details>
    
<details>
<summary><b>Distance to Nearest Park Hurdles</b></summary>
<br/>

Once I had the datasets loaded and cleaned, I shifted my focus on calculating the minimum distance from each location to the nearest park. After some exploration and research, I landed on a method I developed using nested iterations and reprojecting the geometry into a different Coordinate Reference System (CRS) in order to get accurate distances in meters. 

With the distances calculated, a distribution shows a right skew. More of these health points are located closer to 0 kilometes to a park than located 20+ kilometers away. This could present issues in the calculations to come.
    
![Distance Distribution screenshot](https://github.com/derekbeistad/health-and-proximity-to-natural-areas-analysis/blob/main/images/distancedistribution.jpg?raw=true)
To combat this, I grouped the health data into 3 distinct groups.

Distance Groups:
- Close (0km to 3.96km)
- Medium (3.97km - 12.26km)
- Far (12.26km +)

Now we see an even distribution between close, medium, and far health points.
![Distance Group Counts screenshot](https://github.com/derekbeistad/health-and-proximity-to-natural-areas-analysis/blob/main/images/distance-group-count.jpg?raw=true)

Now when we calculate the health values within these groups, we can more accurately compare the results to each group without the worry of sample size variance between them.
    
Here is a map showing both the health points and park locations. The Health points are color coded to inducate if they are located "close", "medium", or "far" from the closest park to them.
![Health and Parks Map](https://github.com/derekbeistad/health-and-proximity-to-natural-areas-analysis/blob/main/images/healthparks-map.jpg?raw=true)
    
[Interactive Folium Map](https://derekbeistad.github.io/Health-and-Proximity-to-Parks-Map/tn_parks.html)
    
</details>

# Conclusions
[(Back to top)](#table-of-contents)
<details>
<summary><b>Health Measure by Distance to Parks</b></summary>
<br/>
Looking at the scatter plot, notice how each measure has a positive, albeit small positive correlation and small R-Squared value, showing significance.
    <br/>
    <br/>
    
![Distance Scatter Plot](https://github.com/derekbeistad/health-and-proximity-to-natural-areas-analysis/blob/main/images/distancescatter.jpg?raw=true)

Looking at the bar graph, we notice that the percentage of these health measures are slightly lower in the close category than in the far category, furthering the relationship.
    
![Distance Bar Chart](https://github.com/derekbeistad/health-and-proximity-to-natural-areas-analysis/blob/main/images/distance-bar.jpg?raw=true)
    
It's important to note that these correlations are small, and there are many other factors that influence these health measures. While proximity to natural areas alone will not positively impact someone's health, it does provide easier access to free physical activity and fresh air.
</details>
<details>
<summary><b>Conclusions and Further Research</b></summary>
<br/>
Overall we saw that there is a slight correlation between health and proximity to natural areas. It is important to note that correlation does not mean causation, as many factors impact someone's health, and being close to a natural area does not imply that the park was used by the locals regularly.
<br/>
Even so, we did see a relationship and more research should be done with more precise locations. It would be interesting to see these health mesaures calculated with respect to park usage in addition to proximity to the parks.
    
![Conclusions Image](https://github.com/derekbeistad/health-and-proximity-to-natural-areas-analysis/blob/main/images/conclusions.jpg?raw=true) 
</details>

<details>
<summary><b>Recommendations</b></summary>
<br/>
The American Heart Association recommends at least 150 minutes of moderate-intensity activity per week (30 minutes per day, 5 x week), but states that 300 minutes (1 hour per day, 5 x week) will increase the benefits seen. This includes a lower risk of heart disease, stroke, diabetes, and high blood pressure. We saw these same measures in our analysis.

Moderate-Intensity Activities Include:
- brisk walking
- dancing
- gardening
- tennis
- biking
- etc.
    
###### Activity recommendations and examples come from the American Heart Association [1]    
</details>


# Link to Dashboard
[(Back to top)](#table-of-contents)

# [Dashboard](https://public.tableau.com/views/health-and-proximity-to-natural-areas/HealthandProximitytoNaturalAreas?:language=en-US&:sid=&:display_count=n&:origin=viz_share_link)

# Resouorces
[(Back to top)](#table-of-contents)

[1] "American Heart Association Recommendations for Physical Activity in Adults and Kids", American Heart Association, 2024 January 19 https://www.heart.org/en/healthy-living/fitness/fitness-basics/aha-recs-for-physical-activity-in-adults

"USA Parks", ArcGIS, 2023 December 27, https://www.arcgis.com/home/item.html?id=578968f975774d3fab79fe56c8c90941

"PLACES: Local Data for Better Health, Place Data 2023 release", CDC, 2023 August 25, https://data.cdc.gov/500-Cities-Places/PLACES-Local-Data-for-Better-Health-Place-Data-202/eav7-hnsx/about_data

"United States Boundary Files", Office of the Secretary of Transportation, 2023 December 07, https://catalog.data.gov/dataset/united-states-boundary-files