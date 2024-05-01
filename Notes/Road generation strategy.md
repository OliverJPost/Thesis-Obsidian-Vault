# Road generation strategy
#type/idea

[[parishProceduralModelingCities]] uses a strategy to generate highways by making them "attracted" by population peaks. These are not actual highways, but more like "main roads". For generating actual highways they could in a zoomed out level be attracted by population, so they go towards the city, but there could be other attraction and repulsion factors:

### Attraction factors:
#### Zoomed out:
- Population
- Jobs

#### Zoomed in
- Passable terrain
- Industry areas
- Office areas
- CBD/American City Center
- Airport

Could be supported by statistics. Average distance to highway for all these things


### Repulsion factors
#### Zoomed out
- ?

#### Zoomed in
- Illegal districts (historic city center)
- Impassable terrain (mountains for longer distance, big bodies of water on short distance. Small bodies of water are okay (bridge))

Each district type and PoI type could have it's own highway attraction and repulsion factor. 


### Getting the right amount of highways
- The goal for the amount of highways can be implied from statistics. A European city will have less highways than an American one. Population will also play a role. A small city might have no highways at all.
- The L-system can be used to generate a candidate network of highways. After that a graph analysis can be done, combined with voronoi diagram to see how much population/jobs each segment of the highways serve. A third factor could be cost, where bridges and mountain highways become very expensive. This, combined with the goal amount of highways can be used to elimante segments until a final network is reached.