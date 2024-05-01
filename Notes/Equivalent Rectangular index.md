---
possible layers:
  - buildings
  - blocks
  - enclosures
  - tessellation
implemented layers: 
scale: single
---
# Equivalent Rectangular index
#type/metric

![[CleanShot 2024-02-08 at 00.15.05@2x.png]]

Calculated using [[MomepyToolkitUrban]]'s `EquivalentRectangularIndex`
Originally from [[basaranerPerformanceShapeIndices2017]]

![[Pasted image 20231214150524.png]]
![[Pasted image 20231214154851.png]]
![[Pasted image 20231214155513.png]]

It forms an improvement over [[rectangularity]] because it's less susceptible to narrow protrusions from the footprint. Instead of using a bounding rectangle it uses a rectangle with the same area as the footprint

![[CleanShot 2023-12-14 at 15.08.04@2x.png]] 