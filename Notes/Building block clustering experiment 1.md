# Building block clustering experiment 27/03
#type/experiment 
- Only blocks with area below 50.000 m2 (because otherwise these big blocks with few houses tend to claim most of the classes)
- K-means++ 5 classes on:
	- Mean [[shared walls ratio]]
	- [[Mean interbuilding distance]]
	- mean building [[area]]
![[image 1.png]]![[CleanShot 2024-03-26 at 14.40.19@2x.png]]
**Cluster 0 “Low Density Residential”**

_This cluster has moderate shared walls ratios, relatively higher mean interbuilding distances, and the lowest mean building area, which suggests these could be low-density residential areas, possibly suburban or semi-rural, with standalone homes and spacious lots._
![[image 6 1.png]]
  
**Cluster 1 "High Density Residential”**

_Characterized by a high shared walls ratio, the lowest mean interbuilding distance, and very small mean building area, this cluster likely represents high-density residential areas, such as apartment complexes or terraced houses, where buildings are close together, and individual unit areas are smaller._
![[image 5 1.png]]
  

  

**Cluster 2 “Spacious and Irregular”**

_With the lowest shared walls ratio, the highest mean interbuilding distance, and the largest mean building area, this cluster could reflect more spacious and irregularly distributed buildings, possibly indicating rural areas, industrial zones, or large estate properties._
![[image 2 1.png]]
  

**Cluster 3 “Mixed Use/Commercial”**

_The highest shared walls ratio, moderate mean interbuilding distance, and a modest mean building area suggest this cluster could be a mix of commercial and residential buildings in urban areas. The high shared walls ratio indicates closely packed structures, typical of commercial downtowns or mixed-use neighborhoods._
![[image 3 1.png]]
  

**Cluster 4 “Dense Urban Residential”**

_With a relatively high shared walls ratio, moderate mean interbuilding distance, and small mean building area, this cluster seems to represent dense urban residential areas, where homes might share walls (like row houses or duplexes) but have a bit more space around them compared to the high-density residential areas of Cluster 1._
![[image 4 1.png]]
![[image 7 1.png]]
![[image 8.png]]
![[image 9.png]]