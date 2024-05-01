---
possible layers:
  - buildings
  - blocks
  - enclosures
  - tessellation
implemented layers: 
scale: single
---
# Elongation
#type/metric

- ! What about this? Values seem incorrect/flipped
![[CleanShot 2024-02-08 at 00.13.16@2x.png]]

Can be calculated with [[MomepyToolkitUrban]]

Based on orge Gil, Nuno Montenegro, J N Beirão, and J P Duarte. On the Discovery of Urban Typologies: Data Mining the Multi-dimensional Character of Neighbourhoods. _Urban Morphology_, 16(1):27–40, January 2012. URL: [http://www.urbanform.org/online_public/2012_1.shtml](http://www.urbanform.org/online_public/2012_1.shtml).

$$
{{p - \sqrt{p^2 - 16a}} \over {4}} \over
{{{p} \over {2}} - {{p - \sqrt{p^2 - 16a}} \over {4}}}
$$
where a is the area of the object and p its perimeter.

![[Pasted image 20231214155711.png]]
![[Pasted image 20231214155714.png]]
![[Pasted image 20231214155717.png]]
![[Pasted image 20231214160031.png]]


 - & Seems like a lower value gives longer buildings, instead of the other way around