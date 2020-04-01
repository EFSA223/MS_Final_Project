# The Interactive Traffic Accidents Map of The Netherlands.

## I. Introduction
Traffic accidents is a problem in every city. Minor accidents with material damage to major accidents with fatal consequences. According to the [World Health Organization (WHO)](https://www.who.int/news-room/fact-sheets/detail/road-traffic-injuries), approximately 1.35 million people die from road accidents every year. In the Netherlands there are approximately xxx traffic accidents and in Curacao 12750. Everyone wants a safe traffic, to realize this everybody has to be informed and I want to do this through a webmap.

I want to design and publish a map that depicts these road accidents so that the public can learn how many tragic accidents happen every day on roads they use and hope that everyone will pay more attention in traffic.

Maybe this can be a build on my last [Map675 project](https://efsa223.github.io/Vehicle_Crashes/), I can expand this with more functionality and combine it with other public issues.

First I want to create a Public Transport map of my island but realty is that there is no structure data available. I had to choose another topic, the "Traffic Accident" of The Netherlands.


## II. Methodology
The file Accidents registered in the Netherlands is a file with the accident reports of the police linked to the digital road network. This data is intended to perform various road safety analyzes and made available by [Bestand geRegistreerde Ongevallen Nederland (BRON)](http://www.nationaalgeoregister.nl/geonetwork/srv/dut/catalog.search#/metadata/4gqrs90k-vobr-5t59-x726-4x2unrs1vawz). I will use the data: "Traffic accidents - Netherlands 2009-2018" and the Netherlands administrative areas.

I also use other demographic data to compare with the data of road accidents and to perform different analyzes. For example, I chose the following themes:
- [Population](https://opendata.cbs.nl/statline/#/CBS/nl/dataset/70072ned/table?ts=1584238008129)
- [Alarms from the fire brigade](https://opendata.cbs.nl/statline/#/CBS/nl/dataset/83122NED/table?ts=1584324297118)
- [Total Motor vehicle fleet](https://opendata.cbs.nl/statline/#/CBS/nl/dataset/7374hvv/table?fromstatweb)

I'm working with ratio data.
The main geometry I'm going to use is points that shows the location of the accidents, and also polygons for the administrative areas.


### A. Data
After downloading the data (see **dataStructure.md**) I imported all csv files into a PostgreSQL database and created the table relations. With a sql-query, I made a selection of the data I need and exported it to a csv file, **VerkeersOngevallenNED_2009-2018.csv**.
QGIS was used to visualize the data and to export to GeoJSON.

**Accident locations**
![*](/images/verOng_11_clean.png)

For this project I will also use data from the Dutch [Central Bureau for Statistics](https://opendata.cbs.nl/statline/#/CBS/nl/). Data downloaded are 1. Population, 2. Alarms from the fire brigade and 3. the total motor vehicle fleet. The structure of this datasets are the same, with four columns.
- _code_,      is the code to identify provincies
- _provicie_,  the 12 administrative areas
- _year_,      years from 2009 - 2018
- _total_,     total per areas

[Datastructure](/dataStructure.md)

### B. Media for delivery
The map will be a web browser-based application accessible across desktop devices.
HTML, CSS, SVG, JavaScript and leaflet/Mapbox will be use to make the web application. Different library will be used with bootstrap as possible framework. For the geospatial data analysis and data manipulation I will use tools from the Turf.js library.

- [Bootstrap](https://getbootstrap.com/)
- [HTML Reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)
- [CSS Reference](https://developer.mozilla.org/en-US/docs/Web/CSS/Reference)
- [Leaflet](https://leafletjs.com/)
- [Mapbox](https://www.mapbox.com/)
- [Turf.js](http://turfjs.org/)
- [Analyze with Turf.js and Mapbox](https://docs.mapbox.com/help/tutorials/analysis-with-turf-mapbox-js/)


### C. Application layout

![*](/images/app_layout02.png)

### D. Thematic representation

#### Map realization
- Show all accident on map
  - Categorize per damages
  - and nature of the Accidents
- Slider, Let user swiftly slide through the years
- Overlay with other socio-demographic Data
  - population
  - Total road vehicles
  - alarms from the fire brigade

#### Challenges
    - killed and seriously injured in traffic
    - fatalities by mode of transport
    - road deaths by province inhabitants
    - How has the number of road deaths in the Netherlands developed over the past ten years?
    - What is the risk per transport mode of dying in traffic?

### E. User interaction
When opening or starting the application a standard map will be projected. The user true searching form will interact with the web application. Selecting different parameters allows targeted filtering.

### F. Aethetics and design considarations

### G. Conclusion
