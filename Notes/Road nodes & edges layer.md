# Road nodes & edges layer
#type/layer

[[Road classes]]
## Process 
- [ ] [[Simplify street network]]
#### Implemented metrics
```dataview
TABLE
FROM #type/metric 
WHERE contains(implemented-layers, "roads")
```
#### Possible metrics
```dataview
TABLE
FROM #type/metric 
WHERE contains(possible-layers, "roads")
```
[[Closeness centrality]]