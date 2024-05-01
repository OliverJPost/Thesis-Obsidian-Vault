# Patch statistics

### Patch level
- area ==R P==
  - area of the patch in m2
- cai Core Area Index ==R P==
  - Percentage of a patch that is core area (a cell that has no neighbors with a differing value)
- circle: Related Circumscribing Circle 
  - ratio between the patch area and the smallest circumscribing circle of the patch. Describes compactness
- contig: Contiguity index 
  - asses the spatial connectedness (contiguity) of cells in patches
- enn: Euclidean Nearest-Neighbor Distance ==P==
  - The distance to the nearest neighbouring patch of the same class i. The distance is measured from edge-to-edge. The metric is a simple way to describe patch isolation.
- frac: Fractal dimension index ==P==
  - The index is based on the patch perimeter and the patch area and describes the patch complexity.
- gyrate: Radius of Gyration 
  - The distance from each cell to the patch centroid is based on cell center to centroid distances. The metric characterises both the patch area and compactness.
- shape: Shape index ==P==
  - It describes the ratio between the actual perimeter of the patch and the square root of patch area and thus adjusting for a square standard. Thus, it is a simple measure of shape complexity.

### Class level
- ai: Aggregation index
  - equals the number of like adjacencies divided by the theoretical maximum possible number of like adjacencies for that class. This index measures the degree to which patches of the same class are grouped together. Higher values indicate that patches are more aggregated, suggesting a more continuous and less fragmented distribution
- area cv, mn, sd
- cai cv mn sd
- circle cv mn sd
- clumpy: Clumpiness index
  - Indicates the degree to which patches of the same class are clumped together versus being randomly distributed. Values closer to 1 indicate a more clumped distribution, while values closer to -1 indicate a more dispersed distribution.
- cohesion: Patch Cohesion Index
  - It characterises the connectedness of patches belonging to class i. It can be used to asses if patches of the same class are located aggregated or rather isolated and thereby COHESION gives information about the configuration of the landscape.
- contig cv mn sd
- core cv mn sd
- edge density
  - The edge density equals the sum of all edges of class i in relation to the landscape area. The metric describes the configuration of the landscape, e.g. because an aggregation of the same class will result in a low edge density.
- enn cv mn sd
- frac cv mn sd
- gyrate cv mn sd
- iji: Interspersion and Juxtaposition index
  - t is a so called "salt and pepper" metric and describes the intermixing of classes. Approaches 0 if a class is only adjacent to a single other class and equals 100 when a class is equally adjacent to all other classes
- lpi: Largest patch index
  - It is the percentage of the landscape covered by the corresponding largest patch of each class i. It is a simple measure of dominance. Approaches LPI = 0 when the largest patch is becoming small and equals LPI = 100 when only one patch is present
- np: Number of patches
- para cv mn sd
- pd: patch density
- pland: Percentage of landscape of class