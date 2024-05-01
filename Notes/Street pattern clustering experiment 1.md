# Street pattern clustering experiment 1
#type/experiment 

![[CleanShot 2024-03-26 at 15.14.06@2x.png]]
![[CleanShot 2024-03-26 at 15.17.49@2x.png]]
almere

Kmeans 5 classes based on 
- mean_neighborhood_block_equivalent_rectangular_index  [[Equivalent Rectangular index]]
- mean_neighborhood_block_circular_compactness [[CircularCompactness]]
- mean_neighborhood_node_distance [[Average node distance]]
- mean_neighborhood_node_degree [[Node degree]]

[[Road contextualizing]] 10 steps

```bash
cluster almere_context.gpkg road_edges mean_neighborhood_block_equivalent_rectangular_index mean_neighborhood_block_circular_compactness mean_neighborhood_node_distance mean_neighborhood_node_degree --column cluster3
```


#### Cluster 0 “Irregular and Fragmented Areas.”
> This cluster has the lowest mean values across most metrics except for mean_neighborhood_node_distance, where it's relatively low, but not the lowest. Its characteristics suggest that it might represent areas with very low block equivalent rectangular index and circular compactness, indicating highly irregular and fragmented urban form. The node degree is also the lowest, suggesting less connectivity. 
![[image 10.png]]
#### Cluster 1 “Structured and Connected Urban Areas”
> This cluster has the highest mean values for block equivalent rectangular index and circular compactness, indicating areas with more regular and compact urban forms. The mean_neighborhood_node_degree is also the highest, pointing to high connectivity. This cluster represents the most structured and connected urban areas. 
![[image 11.png]]
#### Cluster 2 “Moderately Structured Areas.”
> This cluster shows moderate values in all metrics, indicating a balance between irregularity and structure in urban form, with moderate connectivity. It represents areas that are neither highly irregular nor highly structured, with a decent level of connectivity.
![[image 14.png]]
#### Cluster 3: “Transitional Urban Areas.”
> This cluster has low to moderate values across the metrics, with relatively higher standard deviations for mean_neighborhood_block_equivalent_rectangular_index and mean_neighborhood_node_degree, indicating variability within the cluster. These areas might be transitioning or mixed-use urban areas with varying degrees of structure and connectivity. 
![[image 12.png]]
#### Cluster 4: “Sparse and Irregular Areas.”
> This cluster stands out with the highest mean_neighborhood_node_distance, significantly lower mean values for the block equivalent rectangular index and circular compactness, and the lowest mean_neighborhood_node_degree. These characteristics suggest areas with sparse connectivity, large distances between nodes, and highly irregular urban forms. 
![[image 13.png]]

![[image 15.png]]
![[image 16.png]]
![[image 17.png]]
![[image 18.png]]
![[image 20.png]]