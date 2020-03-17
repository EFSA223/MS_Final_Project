# The Netherlands Interactive Traffic Accidents Map.

Traffic accidents is a problem in every city. Minor accidents with material damage to major accidents with fatal consequences. According to the [World Health Organization (WHO)](https://www.who.int/news-room/fact-sheets/detail/road-traffic-injuries), 1.35 million people die from road accidents every year. Everyone wants a safe traffic.

I want to design and publish a map that depicts these road accidents so that the public can learn how many tragic accidents happen every day on roads they use and hope that everyone will pay more attention in traffic.

Maybe this can be a build on my last [Map675 project](https://efsa223.github.io/Vehicle_Crashes/), I can expand this with more functionality and combine it with other public issues.

## Map realization
- Show all accident on map
  - Categorize per damages
  - and nature of the Accidents
- Slider, Let user swiftly slide through the years
- Overlay with other socio-demographic Data
  - population
  - Total road vehicles
  - alarms from the fire brigade

## Challenges
  - killed and seriously injured in traffic
  - fatalities by mode of transport
  - road deaths by province inhabitants
  - How has the number of road deaths in the Netherlands developed over the past ten years?
  - What is the risk per transport mode of dying in traffic?

## Data
First I want to create a Public Transport map of my island but realty is that there is no structure data available.
I had to switch to my thirt topic, the "Traffic Accident" of The Netherlands.
The file Accidents registered in the Netherlands is a file with the accident reports of the police linked to the digital road network. This data is intended to perform various road safety analyzes and made available by [Bestand geRegistreerde Ongevallen Nederland (BRON)](http://www.nationaalgeoregister.nl/geonetwork/srv/dut/catalog.search#/metadata/4gqrs90k-vobr-5t59-x726-4x2unrs1vawz). I will use the data: "Traffic accidents - Netherlands 2009-2018".

Overlay data options:
- [Population](https://opendata.cbs.nl/statline/#/CBS/nl/dataset/70072ned/table?ts=1584238008129)
- [Alarms from the fire brigade](https://opendata.cbs.nl/statline/#/CBS/nl/dataset/83122NED/table?ts=1584324297118)
- [Total road vehicles](https://opendata.cbs.nl/statline/#/CBS/nl/dataset/7374hvv/table?fromstatweb)
- Tne Netherlands administrative areas

I'm working with ratio data.
The main geometry I'm going to use is points that shows the location of the collision, and also polygons for the administrative areas.
