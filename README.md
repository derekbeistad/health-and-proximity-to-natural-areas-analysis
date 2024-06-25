# Health and Proximity to Outdoor Areas in Tennessee

![GitHub last commit](https://img.shields.io/github/last-commit/derekbeistad/health-and-proximity-to-natural-areas-analysis)
![GitHub issues](https://img.shields.io/github/issues-raw/derekbeistad/health-and-proximity-to-natural-areas-analysis)

# Table of Contents <a name="table-of-contents"></a>
- [Table of Contents](#table-of-contents)
- [Motivation](#motivation)
- [Technologies](#technologies)
- [The Data](#the-data)
- [Hurdles](#hurdles)
- [Conclusions](#conclusions)
- [Link to Dashboard](#link-to-dashboard)
- [Resources](#resources)

![Tableau screenshot](https://github.com/derekbeistad/health-and-proximity-to-natural-areas-analysis/blob/workingbranch/images/intro-img.jpg?raw=true)

# Motivation
[(Back to top)](#table-of-contents)
### Does one's proximity to the outdoors affect their overall health?
<details>
    <summary><b>Investigate the relationship between living close to parks and someone's health</b></summary>
<br/>
Staying active is a crucial part of a healthy lifestyle. According to the American Heart Assocciation, 150 minutes a week of moderate-intensity activity can  "Lower the risk of heart disease, stroke, type 2 diabetes, (and) high blood pressure..." [1]. With this information, we want to know if living closer (having easy access) to a park will affects someone's overall health.
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
![Parks Map screenshot](https://github.com/derekbeistad/health-and-proximity-to-natural-areas-analysis/blob/workingbranch/images/parks-map.jpg?raw=true)
![Num of Parks by Type screenshot](https://github.com/derekbeistad/health-and-proximity-to-natural-areas-analysis/blob/workingbranch/images/parks-by-type.jpg?raw=true)
</details>
## Health Data
### From CDC - updated 2023 August 25
https://data.cdc.gov/500-Cities-Places/PLACES-Local-Data-for-Better-Health-Place-Data-202/eav7-hnsx/about_data
<details>
    <summary><b>Health Data Summary</b></summary>
<br/>
- Health data for 429 different locations throughout Tennessee
- Health data is for adults aged 18 and older.
![Health Data Map screenshot](https://github.com/derekbeistad/health-and-proximity-to-natural-areas-analysis/blob/workingbranch/images/health-data-map.jpg?raw=true)
</details>

# Hurdles
[(Back to top)](#table-of-contents)

# Conclusions
[(Back to top)](#table-of-contents)

# Link to Dashboard
[(Back to top)](#table-of-contents)

https://public.tableau.com/views/health-and-proximity-to-natural-areas/HealthandProximitytoNaturalAreas?:language=en-US&:sid=&:display_count=n&:origin=viz_share_link

# Resouorces
[(Back to top)](#table-of-contents)