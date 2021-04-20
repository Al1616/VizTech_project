+++
title = "My presentation"
outputs = ["Reveal"]

[reveal_hugo]
theme = "moon"

+++

### 'Rough' City for Better Air Quality

Ran Ma_VizTech_Spring 21


---

{{< slide id="regular" >}}

### Abstract



{{% section %}}

The research focus on the relation between urban space and urban air quality on the mesoscale and microscale level. Manhattan is the targeted research urban area.

---

The spacial factors of the city, which are extracted from building configurations, are examined to establish a correlation with the local air quality by different time of the day.

{{% /section %}}


---

### Introduction

{{% section %}}

Every year air pollution contributes to millions of early death globally. Residents of the city suffer more from the polluted air. The most common pollutants are fine particulate matter(PM2.5), ground level ozone, and nitrogen dioxide.

---

The source of pollutants could be factories emission, agriculture production, car emission, and even cooking exhaust. Both transboundary pollution coming from the periphery area and local pollution contribute to the air pollution in the city.

---

The building of the city which composes of high-rise and low-rise building change the topography of the land, influencing the wind and air-flow in the urban space. A 'rough' city with high-rise building obstructs the air-flow near the ground.

---

By compressing the air going through the intervals between buildings, high-rise buildings creates a strong convection on the street of city grid. The pollutant either produced by local vehicles or transported from the periphery relies on air convection to disperse and to dissipate.

{{% /section %}}

---


### Methodology

{{% section %}}

The building profiles are edited and generating the features of urban listed urban spae factors. The factors merge with aqi data on the column of census tract number. The correlation is then calculated between the aqi and the space factors.

---

The most relevant features are selected to feed the machine-learning model. Use Lasso to build the regression model. Use Scikit Learns GrisearchCV function to find the best model parameters automatically.

{{% /section %}}

---


### Parameters

{{% section %}}

##### Air Quality

The air quality data is scraped from Breezometer API, with columns of region_id (US census tract number), aqi (air quality index), and pollutant type (including o3, pm10, and no3).

---

##### Air Quality
The census tract divides the Manhattan island into 288 geolocation zone.

---

##### Air Quality
The data is extracted by different times of the day: morning (6 am), noon (1 pm), evening (6 pm), and night (11 pm).

---

##### Air Quality
With the amount limit of scraping the air quality data, the data from three consecutive days (30-03-2021, 31-03-2021, and 01-04-2021) are extracted in order to obtain the mean of aqi for each geolocation at different times of the day.

---

##### Urban Space Factors
The Manhattan building profile is from PLUTO. The building footprint is also obtained.
The following features of urban space factors are created from the raw data:

---

##### Building height
('heightroof')
<br> : is the average of every building roof height within the same census tracts zone. </br>

---

##### Ground Elevation
('groundelev')
<br> : is the average of every building roof height within the same census tracts zone. </br>

---

##### Landuse
For each type of landuse, the percentage of each type within a census tracts zone is obtained by the ratio of the type lot area and the total lot area of the tracts zone.

---

##### Landuse

<br> Ld01: one & two family buildings </br>
<br> Ld02: multi-family walk-up buildings </br>
<br> Ld03: multi-family elevator buildings </br>
<br> Ld04: mixed residential & commercial buildings </br>


---

##### Landuse


<br> Ld05: commercial & office buildings </br>
<br> Ld06: industrial & manufacturing buildings </br>
<br> Ld07: transportation & utility </br>
<br> Ld08: public facilities & institutions </br>

---

##### Landuse

<br> Ld09: open space & outdoor recreation </br>
<br> Ld10: parking facilities </br>
<br> Ld11: vacant land </br>

---

##### Standalone
('alonepct')
<br> : is whether each building is attached to the adjacent ones. The data is area percentage of stand-alone building of the total census tracts lot area. </br>

---

##### FAR
('far')
<br> : is the ratio between total building floor area and total lot area of the census tracts zone. </br>

---

##### Volume
('vol')
<br> : is the total building volume (product of building footprint area and roof height) of the census tracts zone. </br>

---

##### Area Percentage
('pct')
<br> : is the percentage of total floor area of five different programs in the total floor area of the census tracts zone </br>

---

##### Area Percentage
<br>respct: is the residential floor area  </br>
<br>offpct: is the office floor area  </br>
<br>retpct: is the retail floor area  </br>
<br>facpct: is the factory floor area  </br>
<br>strpct: is the storage floor area  </br>

---

##### Assessed Land Value
('assessland')
<br> : is the total assessed land value of the census tracts zone. </br>

---

##### Assessed Total Value
('assesstot')
<br> : is the total assessed value of land and property. </br>

---

##### Emission
<br> : is the green gas emission of the census tracts zone. </br>

---

##### Emission
<br> Totalemission: is the total greenhouse gas emission of the zone</br>
<br> Directemission: is the direct greenhouse gas emission of the zone</br>

---

{{% /section %}}

---

### Result

{{% section %}}

##### Air Quality

<iframe
src = "morn.html"
width = "600"
height = "450"
frameborder = "0"
style = "border:0"></iframe>
<br>Morning Average AQI (6am)</br>

---

##### Air Quality
<iframe
src = "noon.html"
width = "600"
height = "450"
frameborder = "0"
style = "border:0"></iframe>
<br>Noon Average AQI (1pm)</br>

---

##### Air Quality
<iframe
src = "even.html"
width = "600"
height = "450"
frameborder = "0"
style = "border:0"></iframe>
<br>Evening Average AQI (6pm)</br>

---

##### Air Quality
<iframe
src = "night.html"
width = "600"
height = "450"
frameborder = "0"
style = "border:0"></iframe>
<br>Night Average AQI (11pm)</br>

{{% /section %}}

---



### air quality
