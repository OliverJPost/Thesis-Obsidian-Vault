---
aliases: ["Parish et al. Procedural Modeling of Cities"]
tags: [✅, 💎, roads, step/generation, type/reference]
year: 
---
# Procedural Modeling of Cities [📖](zotero://select/library/items/5MKQ3FXP)

> [!abstract]-
> 
> Modeling a city poses a number of problems to computer graphics. Every urban area has a transportation network that follows population and environmental inﬂuences, and often a superimposed pattern plan. The buildings appearances follow historical, aesthetic and statutory rules. To create a virtual city, a roadmap has to be designed and a large number of buildings need to be generated. We propose a system using a procedural approach based on L-systems to model cities. From various image maps given as input, such as land-water boundaries and population density, our system generates a system of highways and streets, divides the land into lots, and creates the appropriate geometry for the buildings on the respective allotments. For the creation of a city street map, L-systems have been extended with methods that allow the consideration of global goals and local constraints and reduce the complexity of the production rules. An L-system that generates geometry and a texturing system based on texture elements and procedural methods compose the buildings.
> 

> [!abstract]- Related Zotero items (1):  
>
> | title | proxy note | desktopURI |
> | --- | --- | --- |
> | L-Systems Considered Harmful | [[@barettLSystemsConsideredHarmful2007]] | [Zotero Link](zotero://select/library/items/6Q5V5ILN) |  |

> [!quote]- Citations
> 
> ```query
> content: "@parishProceduralModelingCities" -file:@parishProceduralModelingCities
> ```

%% begin notes %%
thumb::![[CleanShot 2023-12-16 at 13.02.20@2x.png|canvas-top]] ^a55a34
## Permanent notes
### Initial thoughts:
- One of the most important works on road network generation (or city generation in general)
- Introduces [[L Systems]]

### Relations:
- To understand the street algorithm, it's better to read [[barettLSystemsConsideredHarmful2007]]

### Summary
#### Roads
The road network generation splits generation in two parts, both follow a similar system:
- Highways (main roads really), that are generated based mainly on a population map, but can also be influenced by circular, rectangular, or elevation pattern
- Streets, that are generated either based on population, or more likely on those three types of patterns

The system is officially an [[L Systems|L-system]], but see [[barettLSystemsConsideredHarmful2007]] for an algorithm implementation.

The flow and direction of the streets and street pattern is almost entirely dictated by these so called "global goals" of population and street pattern. They are also checked for "local constraints", but these only change the direction if the roads would otherwise go in an illegal zone or if there is an intersection within snapping distance.

- ! Roads cannot be curved. In the paper they solve this with postprocessing
- ! The street pattern is mainly influenced by global goals, not by local interaction with streets around the candidate street. This can lead to unrealistic networks
- $ The algorithm is quite fast

#### Plots
The plot algorithm is very simple, does not work for convex shapes. Don't think I would use the algorithm

#### Buildings
Also an L-System, but barely described at all in the paper

%% end notes %%
## Reading notes
%% begin annotations %%

Imported on 2023-12-17 17:04



- ? Space Syntax [(p. 1)](zotero://open-pdf/library/items/JTSK4RXP?page=1&annotation=ZX9IX5MA) 
- ? the shape gram- mar [(p. 1)](zotero://open-pdf/library/items/JTSK4RXP?page=1&annotation=N9JPZUJA) 
- & capable of modeling a complete city using a comparatively small set of sta- tistical and geographical input data and is highly controllable by the user. [(p. 1)](zotero://open-pdf/library/items/JTSK4RXP?page=1&annotation=SCCWI2RC) 
- @ the creation of the city is reduced to generating a traffic network and buildings [(p. 1)](zotero://open-pdf/library/items/JTSK4RXP?page=1&annotation=QJK3DHX2) 
- @ Land use data is provided by the user in form of image-maps [(p. 1)](zotero://open-pdf/library/items/JTSK4RXP?page=1&annotation=KGVR35WI) 
- & L-systems have been used in a similar application [20], support branching very well and have the advantage of database amplification [30]; this suggests their potential use to generate convincing large-scale road patterns. [(p. 2)](zotero://open-pdf/library/items/JTSK4RXP?page=2&annotation=52KAZQLF) 
- @ To achieve this, we extended the L-system with a higher- level mechanism that makes the addition of new rules very easy. [(p. 2)](zotero://open-pdf/library/items/JTSK4RXP?page=2&annotation=EQDILE8S) **Is this known or closed source?** 
- @ In a first step, the input data is fed to the road-generation system, using an extended L-system described in 3.4. The areas between the roads are then subdivided to define the allotments the buildings are placed on. In a third step, by applying another L-system, the buildings are generated as a string representation of boolean operations on simple solid shapes. [(p. 2)](zotero://open-pdf/library/items/JTSK4RXP?page=2&annotation=IW2BCIHR) 
- @ Geographical Maps - Elevation maps - Land/water/vegetation maps • Sociostatistical maps - Population density - Zone maps (residential, commercial or mixed zones) - Street patterns (control behavior of streets) - Height maps (maximal house height) [(p. 2)](zotero://open-pdf/library/items/JTSK4RXP?page=2&annotation=MDJDDRKM) **Input for street network** 
- @ According to [12], not all roads change the population density of their immediate local surroundings, e.g. roads connecting two cities. We therefore chose to consider two types of roads: high- ways and streets. They differ in their purpose and behavior: Highways connect areas with highly concentrated population globally, by scanning the population density input map for peaks. Streets cover the areas between highways according to local population density, giving all neighborhoods transportation access to the nearest highway. Together, these two classes form the road map of the virtual city [(p. 2)](zotero://open-pdf/library/items/JTSK4RXP?page=2&annotation=946YSFCB) **So it's split in just two classes and the highways just connect population peaks** 

- $ **Looks like it's not reacting to water that well**  [(p. 2)](zotero://open-pdf/library/items/JTSK4RXP?page=2&annotation=V46Y3PZI) ![[_Vault/_Attachments/image-2-x308-y443.png]]


### CREATING THE STREET MAP

- @ Every time a new constraint is implemented, many rules have to be rewritten. This makes extensibility a very difficult task. Thus, instead of trying to set the parameters of the modules inside the productions, the L-system creates only a generic template at each step. We call this generic template the ideal successor. [(p. 3)](zotero://open-pdf/library/items/JTSK4RXP?page=3&annotation=4J79EHGM) 
- @ the setting and the modification of parameters in the L-system modules have been ported to external functions. [(p. 3)](zotero://open-pdf/library/items/JTSK4RXP?page=3&annotation=2LMYT25H) 
- & globalGoals [(p. 3)](zotero://open-pdf/library/items/JTSK4RXP?page=3&annotation=A4AJMVR9) 
- & localConstraints [(p. 3)](zotero://open-pdf/library/items/JTSK4RXP?page=3&annotation=QX4ZT3AP) 
- & Every time the rules are applied to an existing string of modules, the following actions are executed: • Return the ideal successor by the L-system. The parameters of the modules are unassigned. <br />
• Call the globalGoals function. This function determines the parameter values of the dominant global goals. All parameter values are set. [(p. 3)](zotero://open-pdf/library/items/JTSK4RXP?page=3&annotation=4529JAFJ) 
- ! Call the localConstraints function. The parameters are checked within the local constraints of the environment.  The parameter values are adjusted to fit these constraints. If this function cannot find suitable parameters, it sets the state flag to FAILED and the module is subsequently deleted. [(p. 3)](zotero://open-pdf/library/items/JTSK4RXP?page=3&annotation=REEACEEB) **So local constraints are only considered all the way at the end. This might be why the result didn't seem to interact with the water features that well. This might mean it won't work well with rivers either.** 
- & The roadmap creation tool distinguishes between the following global goals and local constraints. <br />
• global: street patterns and population density • local: land/water/park boundaries, elevation, crossing of streets [(p. 3)](zotero://open-pdf/library/items/JTSK4RXP?page=3&annotation=8MYSURUK) 
- @ ω: R(0, initialRuleAttr) ?I(initRoadAttr, UNASSIGNED) p1: R(del, ruleAttr) : del<0 → ε p2: R(del, ruleAttr) > ?I(roadAttr,state) : state==SUCCEED {globalGoals(ruleAttr,roadAttr) creates the parameters for: pDel[0-2], pRuleAttr[0-2], pRoadAttr[0-2]} → +(roadAttr.angle)F(roadAttr.length) B(pDel[1],pRuleAttr[1],pRoadAttr[1]), B(pDel[2],pRuleAttr[2],pRoadAttr[2]), R(pDel[0],pRuleAttr[0]) ?I(pRoadAttr[0],UNASSIGNED) p3: R(del, ruleAttr) > ?I(roadAttr, state) : state==FAILED → ε p4: B(del, ruleAttr, roadAttr) : del>0 → B(del-1, ruleAttr, roadAttr) p5: B(del, ruleAttr, roadAttr) : del==0 → [R(del, ruleAttr)?I(roadAttr, UNASSIGNED)] p6: B(del,ruleAttr,roadAttr) : del<0 → ε p7: R(del,ruleAttr) < ?I(roadAttr,state) : del<0 → ε p8: ?I(roadAttr,state) : state==UNASSIGNED {localConstraints(roadAttr) adjusts the parameters for: state, roadAttr} → ?I(roadAttr, state) p9: ?I(roadAttr,state) : state!=UNASSIGNED → ε [(p. 3)](zotero://open-pdf/library/items/JTSK4RXP?page=3&annotation=F67J9CF6) 
### Global Goals for road creation

- @ Highways connect centers of population. To find the next population center, every highway road-end shoots a number of rays radially within a preset radius. Along this ray, samples of the population density are taken from the population density map. <br />
The population at every sample point on the ray is weighted with the inverse distance to the roadend and summed up. The direction with the largest sum is chosen for continuing the growth. [(p. 3)](zotero://open-pdf/library/items/JTSK4RXP?page=3&annotation=38MDNZ4B) 
- @ On the contrary, streets do not change their direction by following the steepest gradient of the population density map. Typically they follow the dominant street pattern. This is reasonable, since most streets in urban areas are built following a superimposed pattern plan. The created street ends still lower the population density in their environment, usually within the area of the block, according to the mechanisms proposed for Open L-systems [20]. When an area with no population is reached, the streets stop growing. [(p. 4)](zotero://open-pdf/library/items/JTSK4RXP?page=4&annotation=K6638B8T) 
### Local constraints

- @ The localConstraints function executes the two following steps: • check if the road segment ends inside or crosses an illegal area. <br />
• search for intersection with other roads or for roads and crossings that are within a specified distance to the segment end. [(p. 4)](zotero://open-pdf/library/items/JTSK4RXP?page=4&annotation=MWP76KG3) 

- @ ****  [(p. 4)](zotero://open-pdf/library/items/JTSK4RXP?page=4&annotation=XWJ7SJ6N) ![[_Vault/_Attachments/image-4-x302-y623.png]]



- $ ****  [(p. 4)](zotero://open-pdf/library/items/JTSK4RXP?page=4&annotation=ZWCZ72KY) ![[_Vault/_Attachments/image-4-x307-y481.png]]



- $ ****  [(p. 4)](zotero://open-pdf/library/items/JTSK4RXP?page=4&annotation=8JQTA5IX) ![[_Vault/_Attachments/image-4-x302-y323.png]]


- @ If the first check determines that the road end is inside water, a park or another illegal area, the system tries to readjust the values for the road segment in the following ways. <br />
• Prune the segment length up to a certain factor so that it fits inside the legal area of the starting point. <br />
• Rotate the segment within a maximal angle until it is completely inside the legal area. This allows the creation of roads that follow a coastline or a park boundary. <br />
• Highways are allowed to cross illegal area up to a specified length. The generated highway segment is flagged. At the geometry creation stage it can then be replaced by e.g. a bridge, or two tunnel entrances on both sides. [(p. 5)](zotero://open-pdf/library/items/JTSK4RXP?page=5&annotation=I7CNFVC4) 
- @ If the localConstraints function finds a street within the given radius of the end of a segment it can modify the parameters for the following events illustrated in figure 8: • two streets intersect → generate a crossing. <br />
• ends close to an existing crossing → extend street, to reach the crossing. <br />
• close to intersecting → extend street to form intersection. <br />
If a crossing is generated, a new node and two edges in the existing street graph have to be created. After a crossing is generated, a road stops growing. [(p. 5)](zotero://open-pdf/library/items/JTSK4RXP?page=5&annotation=S2KIRE5P) 

- @ ****  [(p. 5)](zotero://open-pdf/library/items/JTSK4RXP?page=5&annotation=GP6VXYTT) ![[_Vault/_Attachments/image-5-x48-y256.png]]



- $ ****  [(p. 5)](zotero://open-pdf/library/items/JTSK4RXP?page=5&annotation=GJD63CLN) ![[_Vault/_Attachments/image-5-x305-y471.png]]


### MODELING OF BUILDINGS

- @ After the creation of highways and streets the populated area of the city is subdivided into many small areas which we call blocks. [(p. 5)](zotero://open-pdf/library/items/JTSK4RXP?page=5&annotation=ICAZJH9T) 
- ! We assume that most of these allotments are convex and rectangularly shaped. The system therefore forbids the creation of concave allotments. [(p. 5)](zotero://open-pdf/library/items/JTSK4RXP?page=5&annotation=27XFAP57) 
- @ A block is divided into smaller units using a simple, recursive algorithm that divides the longest edges that are approximately parallel until the the subdivided lots are under a threshold area specified by the user [(p. 5)](zotero://open-pdf/library/items/JTSK4RXP?page=5&annotation=MG9PR9MU) 
- & the user can control the maximum height of a building through the usage of an image map [(p. 5)](zotero://open-pdf/library/items/JTSK4RXP?page=5&annotation=JVSNWAF5) 

- $ ****  [(p. 5)](zotero://open-pdf/library/items/JTSK4RXP?page=5&annotation=FHZF6UXL) ![[_Vault/_Attachments/image-5-x304-y124.png]]



- $ ****  [(p. 6)](zotero://open-pdf/library/items/JTSK4RXP?page=6&annotation=699UXBDF) ![[_Vault/_Attachments/image-6-x47-y495.png]]





Imported on 2024-04-30 23:30




- $ **Looks like it's not reacting to water that well**  [(p. 2)](zotero://open-pdf/library/items/JTSK4RXP?page=2&annotation=V46Y3PZI) ![[_Vault/_Attachments/image-2-x308-y443.png]]





%% end annotations %%



%% Import Date: 2024-05-01T00:52:43.242+02:00 %%
