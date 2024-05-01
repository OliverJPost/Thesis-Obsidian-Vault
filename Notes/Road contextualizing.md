# Road Contextualizing

![[CleanShot 2024-03-26 at 15.53.42@2x.png]]
![[image 19.png]]
10 steps of contextualizing


#### Original ideas:
#### Simply grab features in a set radius around the cell
![[image 23.png]]
Pros:
- Simple
Cons:
- Not weighted, can produce weird results and unnatural sudden shifts (that are not representative of a style shift in the current cell)
#### Grab features in radius around cell and apply IDW interpolation (on anything outside the cell?)
Pros:
- Simple
- With weighting it can prevent unnatural sudden shifts
Cons:
- Smooth, does not capture borders between styles
#### Combination of the two, but with district constraint based on tertiary+ roads
![[CleanShot 2024-02-09 at 11.18.05@2x.png]]
![[Untitled_Artwork.jpg]]
![[image 2 2.png]]
Pros:
- Same pros as IDW weighting
- Due to limiting, more chance of good and abrupt style change borders
Cons:
- Complex to implement
- Still doesn’t capture all style changes (see example above, two styles within one district)
- Some cities have areas where almost every road is tertiary+ (LA city center), which would result in no features at all being selected (counteract with minimum area?)
==Perhaps best option for buildings and PoI?==
#### Perform road statistics on higher level of grid and have smaller cell inherit all
![[image 3 2.png]]
Pros:
- Simple to implement
- Faster
- Scale of higher level grid is more appropriate for road level analysis
Cons:
- Similarly as the simple radius method, but not even with equal radius around the current grid cell
- What is the point of using a smaller grid when a lot of attributes will be inferred from the higher level grid anyway
#### N closest features
![[image 4 2.png]]
Pros:
- Always have a sufficiently big enough set of data to work with
- Easy to implement
Cons:
- Network might be disconnected
- Unrepresentative for sparse network, where there are no roads nearby (max distance?)
- Still doesn’t capture street typology in example above

#### Recursive network growing based on closest road
![[image 5 3.png]]
Pros:
- Depending on graph implementation, could be easy to implement
- Could even add constraint that it can’t grow past tertiary+ road nodes
- Always have connected network
- Can even be an extra metric to see the area of the bounding box of the grown network
- In example above, it is the best when it comes to capturing the style of the place of the current cell
- Always sufficiently big amount of data
Cons:
- Might give unpredictable results on different road styles and therefore influence the validity of the statistics?
- Leaf streets should be taken care of, perhaps it could start from the closest street and ignore any leafs as starting point?
![[CleanShot 2024-02-09 at 12.00.32@2x.png]]
- Might go much further in one direction than the other if segments on that side are longer (Perhaps recursively grow a certain distance instead of a certain amount of steps?)
==Perhaps best option for roads?==
