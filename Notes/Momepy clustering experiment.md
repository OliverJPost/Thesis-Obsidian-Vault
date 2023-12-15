# Momepy clustering experiment
#type/experiment

Followed the guide [Momepy Clustering Guide](http://docs.momepy.org/en/stable/examples/clustering.html) which is a simplified implementation of [[fleischmannMethodologicalFoundationNumerical2022]]

Used Delft as an example.

Had to downgrade to shapely 2.0.1 because of a bug 
Had to disable `interbuilding_distance` calculation because it resulted in `NaN` values

![[Pasted image 20231214143421.png]]
[[Equivalent Rectangular index]] (left), [[Elongation]] (right)

![[Pasted image 20231214143502.png]]
[[Convexity]] (left), [[linearity]] (right)
- ~ The linearity seems to be mainly dependent on where he network edges split, not actual road network