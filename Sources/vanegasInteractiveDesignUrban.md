---
aliases: ["Vanegas et al. Interactive Design of Urban Spaces using Geometrical and Behavioral Modeling"]
tags: [✅, 🔹, buildings, districts, plots, roads, step/generation, type/reference]
year: 
---
# Interactive Design of Urban Spaces using Geometrical and Behavioral Modeling [📖](zotero://select/library/items/MBHIP49G)

> [!abstract]-
> 
> The main contribution of our work is in closing the loop between behavioral and geometrical modeling of cities. Editing of urban design variables is performed intuitively and visually using a graphical user interface. Any design variable can be constrained or changed. The design process uses an iterative dynamical system for reaching equilibrium: a state where the demands of behavioral modeling match those of geometrical modeling. 3D models are generated in a few seconds and conform to plausible urban behavior and urban geometry. Our framework includes an interactive agent-based behavioral modeling system as well as adaptive geometry generation algorithms. We demonstrate interactive and incremental design and editing for synthetic urban spaces spanning over 200 square kilometers.
> 

> [!quote]- Citations
> 
> ```query
> content: "@vanegasInteractiveDesignUrban" -file:@vanegasInteractiveDesignUrban
> ```

%% begin notes %%
thumb::![[Pasted image 20231212122946.png|canvas-top]]
## Permanent notes
### Initial thoughts:
- Results look very good! Both distribution wise and street system wise
- Seems like it's still restricted to grid, radial, and organic layouts
- Uses raster as input

### Relations:


### Summary
The main focus of the paper is on the dynamic regeneration of the different influence maps (jobs, population, land value, accessibility). It also includes a novel algorithm for generating street networks, but this only does grid or radial and there seems to be no direct way to make it do more than grid or radial.

Maybe the regeneration system can be used for user input or as inspiration for the original generation of the grid.
- & This paper introduces the spatial data grid, and has a mathematical (set?) notation for how it's used. 


%% end notes %%
## Reading notes
%% begin annotations %%


Imported on 2023-12-17 18:34



- & The main contribution of our work is in closing the loop between behavioral and geometrical modeling of cities. [(p. 1)](zotero://open-pdf/library/items/JJU82PFE?page=1&annotation=LSW4PNVX) 
- **It's agent based AND fast? How?** [(p. 1)](zotero://open-pdf/library/items/JJU82PFE?page=1&annotation=C48P3ZP2)
- % The consequences of changing one variable can vary from local to global changes. Consider the following examples: • a designer increases the height of the buildings in a downtown area; as a consequence, the number of jobs and the population increase; this should result in more local streets and residential buildings appearing in another part of the city that is conveniently accessible from the newly altered downtown; • a designer inserts a highway into the model; as a consequence, the accessibility between different parts of the urban space may change, hence the location of jobs, houses, and buildings may have to be drastically altered; and • a designer modifies a subset of the terrain or increases the local population; as a consequence, the geometric configuration of the local neighborhood of streets, city blocks, parcels, and buildings must be updated to accommodate either the modified terrain slopes or the increase in population.  Ignoring these changes may result in models that do not resemble real-world urban spaces such as tall buildings on top of mountains, cities with only skyscrapers and no residential areas, or an imbalance between road networks and buildings. [(p. 2)](zotero://open-pdf/library/items/JJU82PFE?page=2&annotation=59UTQAAS) 
- & UrbanSim [(p. 2)](zotero://open-pdf/library/items/JJU82PFE?page=2&annotation=2EZ2BJU9) 
- @ Building envelopes are procedurally generated and their size is estimated from the population and jobs count that they are to contain. [(p. 2)](zotero://open-pdf/library/items/JJU82PFE?page=2&annotation=GAKBIGK3) 
- @ Our system consists of ܰ urban space variables defined over a 2D spatial domain. Each variable is sampled over a 2D spatial grid ܩ of size ܹൈܪ. [(p. 3)](zotero://open-pdf/library/items/JJU82PFE?page=3&annotation=AJZ78CCS) **They also use a grid overlay of "urban space variables!!!** 
- & We use ݒ ௞to denote the values of the ݇-th state variable throughout the entire spatial grid, and ݒ௞ሺ݅, ݆ሻ to denote the value of the ݇-th state variable at grid cell ሺ݅, ݆ሻ , for ݇ א ሾ1, ܰሿ, ݅ א ሾ1, ܹሿ, and ݆ א ሾ1, ܪሿ. We represent the change of each variable by the differential equation ݒሶ ௞ሺ݅, ݆ሻ ൌ ݂௞ሺݒଵ, ݒଶ,…ݒேሻ. [(p. 3)](zotero://open-pdf/library/items/JJU82PFE?page=3&annotation=N3AQJPPF) 
- @ If a variable ݒ௖, for some value ܿ א ሾ1, ܰሿ, is changed by the user, the system iteratively updates the other variables in order to return to a state of equilibrium. [(p. 3)](zotero://open-pdf/library/items/JJU82PFE?page=3&annotation=RKRCQLV2) 
- @ an urban area of only 10 ൈ 10  kilometers typically consists of 100 ൈ 100 cells, each of 100 ൈ 100  meters [(p. 3)](zotero://open-pdf/library/items/JJU82PFE?page=3&annotation=ZGTDFILP) **They also use 100x100m resolution** 
- @ Based on Waddell and Ulfarsson [2004], we select a minimal set of design variables (i.e., specific instances of the ݒ௞ሺ݅, ݆ሻ’s): • population count ݌ሺ݅, ݆ሻ, corresponding to the number of people who live in the grid cell, and • job count ܾሺ݅, ݆ሻ, referring to the number of jobs (total employment) in the grid cell. [(p. 4)](zotero://open-pdf/library/items/JJU82PFE?page=4&annotation=G4AA8RY4) 
- & we also use per grid cell values for accessibility ܽሺ݅, ݆ሻ and land value ݈ሺ݅, ݆ሻ. While these values could be user-specified parameters, we found them less intuitive and thus only provide algorithms to compute them automatically [(p. 4)](zotero://open-pdf/library/items/JJU82PFE?page=4&annotation=ERAF4X4N) 
- @ For a grid cell ሺ݅, ݆ሻ we define • roads length ݎሺ݅, ݆ሻ, the total length of the roads inside the grid cell, • average tortuosity ߬ሺ݅, ݆ሻ, the mean ratio between the road segment length and the distance between the road segment endpoints for the roads inside the grid cell, • building volume ݉ሺ݅, ݆ሻ, the total volume of interior space within the building structures of the grid cell, and • terrain elevation ݄ሺ݅, ݆ሻ, the average elevation of the terrain inside to the grid cell – in our current work, this variable is only under user control. [(p. 4)](zotero://open-pdf/library/items/JJU82PFE?page=4&annotation=W2BEJFL4) 
- @ Furthermore, parcel size and land use are other design variables but are computed algorithmically [(p. 4)](zotero://open-pdf/library/items/JJU82PFE?page=4&annotation=KUEBD777) 
### Estimating Accessibility and Land Value

- % The accessibility ܽሺ݅, ݆ሻ and land value ݈ሺ݅, ݆ሻ of grid cell ሺ݅, ݆ሻ is calculated using a logistic function. Accessibility ܽሺ݅, ݆ሻ is a measure of the access that grid cell ሺ݅, ݆ሻ has to jobs and to the rest of the population. An intuitive behavior for accessibility is that it decreases with the slope of the terrain and increases with improved connectivity to roads, population and jobs, water fronts and river banks [Ortúzar and Willumsen 2001]. Good connectivity can be implied by geometric closeness or good access via the transportation network (e.g., highway).  To represent accessibility, we use the logistic function ܽሺ݅, ݆ሻ ൌ 1 1൅݁ି௭ሺ௜,௝ሻ (4) where ݖሺ݅, ݆ሻ ൌ ߚ ൅ ଴ߚଵݑଵሺ݅, ݆ሻ ൅ ߚଶݑଶሺ݅, ݆ሻ ൅ ߚଷݑଷሺ݅, ݆ሻ. The variable ݑଵ is an estimate of proximity of grid cell ሺ݅, ݆ሻ to local roads weighted by their relative importance and distance, ݑଵሺ݅, ݆ሻ ൌ ݓ௛݀݅ݐݏሺܴுሻ ൅ ݓ௥݀݅ݐݏሺܴ஺ሻ ൅ ݓ௦݀݅ݐݏሺܴௌሻ (5) where ݓ௛, ݓ௥, and ݓ௦ are the weights of relative importance of the normalized distance measures, ݀݅ݐݏሺߕሻ returns distance from the grid cell center to the closest segment of ߕ, where ߕ can be one of highways ܴு, avenues ܴ஺, or streets ܴௌ, ݑଶ represents the local slope of the terrain, and ݑଷሺ݅, ݆ሻ ൌ ∑ ஽೔ೝೕೝ ௗ೔ೕ,೔ೝೕೝ ௥ (6) is a distance normalized measure of the activity level at ሺ݅, ݆ሻ based on a sampling of ܴ neighboring grid cells ሼሺ݅௥, ݆௥ሻሽ where ݎ א ሾ1, ܴሿ. The value ݀௜௝,௜ೝ௝ೝ is the distance from grid cell ሺ݅, ݆ሻ to grid cell ሺ݅௥, ݆௥). ܦ ೝ௝ೝ௜is a measure of the activity level at grid cell ሺ݅௥, ݆௥ሻ and is computed as the sum of ݌ሺ݅௥, ݆௥ሻ ൅ ܾሺ݅௥, ݆௥ሻ. The empirically determined constants ߚ௢, ߚଵ, ߚଶ, and ߚଷ provide the relative importance of the factors that affect accessibility. Land value ݈ሺ݅, ݆ሻ is calculated using a logistic function similar to (5).  Figure 3 shows how by quickly changing job distribution, the system automatically creates a new population center including its roads, parcels, and buildings connected to the original town. [(p. 5)](zotero://open-pdf/library/items/JJU82PFE?page=5&annotation=HWK45BB6) 
- & generate the roads that correspond to per grid cell road length values ݎሺ݅, ݆ሻ, [(p. 5)](zotero://open-pdf/library/items/JJU82PFE?page=5&annotation=VX4HCR4N) 
- & Adapting from [AASHTO 2004], we classify roads into three types based on their size: (i) highways, which are the highest capacity roads with limited access and carry inter-city traffic and, in large cities, intracity traffic; (ii) arterials, which are lower capacity than highways, carry intra-city traffic and connect to local streets and to highways; and (iii) streets, which are local roads that route traffic from [(p. 5)](zotero://open-pdf/library/items/JJU82PFE?page=5&annotation=D3GF58BY) 

- $ ****  [(p. 5)](zotero://open-pdf/library/items/JJU82PFE?page=5&annotation=8IJIFKCK) ![[_Vault/_Attachments/image-5-x48-y68.png]]


- & Our road generation method is based on the following observations about real-world roads. (a) Road networks are designed and built to meet a transportation demand by the population [Montes de Oca and Levinson 2006]. The capacity of a road, reflected by its width and the mean distance between its consecutive intersections, responds to such a demand. (b) Road networks exhibit a variety of styles which are difficult to be solely inferred from behavioral and geometrical parameters. While highways are usually designed to minimize travel distances, arterials and streets are more affected by historical and aesthetic factors [(p. 6)](zotero://open-pdf/library/items/JJU82PFE?page=6&annotation=AUY4XT7L) 
- ! Our road generation algorithm uses the following key assumptions: • the predominant patterns of arterials and streets are grid style and radial style with spurious occurrences of dead-ends, • in the grid style, up to four nearly-perpendicular segments depart from each intersection point, • in the radial style, three or more road segments depart from some intersection points at equally spaced angles, and • the road pattern and its tortuosity is affected by the nearby population and jobs [(p. 6)](zotero://open-pdf/library/items/JJU82PFE?page=6&annotation=UWXPSUZV) 
- @ To obtain a set of ߢ seeds for generating arterial roads, we group grid cells using a weighted ݇-means clustering algorithm [(p. 6)](zotero://open-pdf/library/items/JJU82PFE?page=6&annotation=MRNYWWGW) 
- [ ] **important. Gives a nice distribution of natural road curvature**:
	- & A seed ݏ௨ has ݉ departing directions Θ௨ ൌ ሼߠ଴, ߠଵ,…,ߠ௠ିଵሽ along which new road segments can be generated. The value of ߠ௞, for ݇൐0, is given by ߠ ௞ൌ ߠ ൅ ଴ଶగ௞ ௠ ൅ ߳, where ߳ is a random variable with distribution ߳~ܰሺ0, ߪଶሻ, ߪ is a small constant, and ߠ ଴is a reference angle. The reference angle is equal to the orientation of the road segment to which the seed is attached. [(p. 6)](zotero://open-pdf/library/items/JJU82PFE?page=6&annotation=VNQDBPUT) 

- $ ****  [(p. 6)](zotero://open-pdf/library/items/JJU82PFE?page=6&annotation=YW7YRZDP) ![[_Vault/_Attachments/image-6-x40-y70.png]]


### Generating Parcels

- @ our method geometrically partitions the city block (e.g., as in Parish and Mueller [2001] or Aliaga et al. [2008]) into parcels. [(p. 7)](zotero://open-pdf/library/items/JJU82PFE?page=7&annotation=GGL924KP) 

- $ ****  [(p. 7)](zotero://open-pdf/library/items/JJU82PFE?page=7&annotation=ATVAVYDT) ![[_Vault/_Attachments/image-7-x48-y434.png]]


- @ The building type, which implicitly reflects land use, is determined by inspecting the ratio of number of jobs to the population size and a building type is chosen from a small database of procedural building styles. In particular, (i) a commercial building is assigned to a parcel with high job count and low population, (ii) a residential building is allocated to a parcel with nearly zero jobs and high population, (iii) an industrial building is placed on a parcel with a medium-level job count and nearly zero population, and (iv) a parcel with only a low population is assigned a house. [(p. 8)](zotero://open-pdf/library/items/JJU82PFE?page=8&annotation=KF3UH5GQ) **They determine building type and land use just from population and jobs** 

- $ ****  [(p. 10)](zotero://open-pdf/library/items/JJU82PFE?page=10&annotation=BBQR8BXH) ![[_Vault/_Attachments/image-10-x45-y583.png]]





%% end annotations %%



%% Import Date: 2024-05-01T00:52:43.558+02:00 %%
