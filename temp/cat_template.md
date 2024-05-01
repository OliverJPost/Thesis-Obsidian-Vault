---
aliases: ["Yoav I H Parish, Pascal Müller (Error: `format` can only be applied to dates. Tried for format object) Procedural Modeling of Cities"]
Title: "Procedural Modeling of Cities"
tags: zotero, literature-notes, reference
Type: journalArticle
---
# Yoav I H Parish, Pascal Müller (Error: `format` can only be applied to dates. Tried for format object) Procedural Modeling of Cities
## Abstract
Modeling a city poses a number of problems to computer graphics. Every urban area has a transportation network that follows population and environmental inﬂuences, and often a superimposed pattern plan. The buildings appearances follow historical, aesthetic and statutory rules. To create a virtual city, a roadmap has to be designed and a large number of buildings need to be generated. We propose a system using a procedural approach based on L-systems to model cities. From various image maps given as input, such as land-water boundaries and population density, our system generates a system of highways and streets, divides the land into lots, and creates the appropriate geometry for the buildings on the respective allotments. For the creation of a city street map, L-systems have been extended with methods that allow the consideration of global goals and local constraints and reduce the complexity of the production rules. An L-system that generates geometry and a texturing system based on texture elements and procedural methods compose the buildings.
> [!header]+
> > [!important]-
> > ```dataview
> > Table rows.important as ""
> > where file.name = this.file.name
> > group by tag
> 
> > [!metadata]-
> > [[Index]] 
> > Yoav I H Parish, Pascal Müller (Error: `format` can only be applied to dates. Tried for format object) Procedural Modeling of Cities
> > Authors:: [[Yoav I H Parish]], [[Pascal Müller]] 
> > Item_Type:: [[journalArticle]]
> >  
> > Citekey:: parishProceduralModelingCities
> > Subjects:: [[roads]], [[step/generation]], [[type/reference]] 
> > Related::  [[barettLSystemsConsideredHarmful2007]]  
> > Attachments:
> > [Parish and Müller - Procedural Modeling of Cities.pdf](file:///Users/ole/Zotero/storage/JTSK4RXP/Parish%20and%20Müller%20-%20Procedural%20Modeling%20of%20Cities.pdf).
> 
> > [!reading]-
> > ```dataview
> > task from #todo/readinglist 
> > where file.name = this.file.name
> > ```
> > ```dataview
> > task from #researchprompt
> > where file.name = this.file.name
> > ```
## Annotations

#idea:: [[Idea]]  <span class="idea">"Space Syntax"</span> [p.1](zotero://open-pdf/library/items/JTSK4RXP?page=1)

#idea:: [[Idea]]  <span class="idea">"the shape gram- mar"</span> [p.1](zotero://open-pdf/library/items/JTSK4RXP?page=1)

"capable of modeling a complete city using a comparatively small set of sta- tistical and geographical input data and is highly controllable by the user." [p.1](zotero://open-pdf/library/items/JTSK4RXP?page=1) 

#important:: [[Important]]  <span class="important">"the creation of the city is reduced to generating a traffic network and buildings"</span> [p.1](zotero://open-pdf/library/items/JTSK4RXP?page=1)

#important:: [[Important]]  <span class="important">"Land use data is provided by the user in form of image-maps"</span> [p.1](zotero://open-pdf/library/items/JTSK4RXP?page=1)

"L-systems have been used in a similar application [20], support branching very well and have the advantage of database amplification [30]; this suggests their potential use to generate convincing large-scale road patterns." [p.2](zotero://open-pdf/library/items/JTSK4RXP?page=2) 

#important:: [[Important]]  <span class="important">"To achieve this, we extended the L-system with a higher- level mechanism that makes the addition of new rules very easy."</span> [p.2](zotero://open-pdf/library/items/JTSK4RXP?page=2)


> [!confusion]+
> #confusion:: [[Confusion]] [[Cat]] <span class="confusion">"Is this known or closed source?"</span> [p.2](zotero://open-pdf/library/items/JTSK4RXP?page=2)
#important:: [[Important]]  <span class="important">"In a first step, the input data is fed to the road-generation system, using an extended L-system described in 3.4. The areas between the roads are then subdivided to define the allotments the buildings are placed on. In a third step, by applying another L-system, the buildings are generated as a string representation of boolean operations on simple solid shapes."</span> [p.2](zotero://open-pdf/library/items/JTSK4RXP?page=2)

#important:: [[Important]]  <span class="important">"Geographical Maps - Elevation maps - Land/water/vegetation maps • Sociostatistical maps - Population density - Zone maps (residential, commercial or mixed zones) - Street patterns (control behavior of streets) - Height maps (maximal house height)"</span> [p.2](zotero://open-pdf/library/items/JTSK4RXP?page=2)


> [!confusion]+
> #confusion:: [[Confusion]] [[Cat]] <span class="confusion">"Input for street network"</span> [p.2](zotero://open-pdf/library/items/JTSK4RXP?page=2)
![[temp/img/parishProceduralModelingCities/image-2-x308-y443.png]]

> [!reading]+ To Read
> - [ ] #todo/readinglist Looks like it's not reacting to water that well [p.2](zotero://open-pdf/library/items/JTSK4RXP?page=2)
#important:: [[Important]]  <span class="important">"According to [12], not all roads change the population density of their immediate local surroundings, e.g. roads connecting two cities. We therefore chose to consider two types of roads: high- ways and streets. They differ in their purpose and behavior: Highways connect areas with highly concentrated population globally, by scanning the population density input map for peaks. Streets cover the areas between highways according to local population density, giving all neighborhoods transportation access to the nearest highway. Together, these two classes form the road map of the virtual city"</span> [p.2](zotero://open-pdf/library/items/JTSK4RXP?page=2)


> [!confusion]+
> #confusion:: [[Confusion]] [[Cat]] <span class="confusion">"So it's split in just two classes and the highways just connect population peaks"</span> [p.2](zotero://open-pdf/library/items/JTSK4RXP?page=2)
#### CREATING THE STREET MAP
#important:: [[Important]]  <span class="important">"Every time a new constraint is implemented, many rules have to be rewritten. This makes extensibility a very difficult task. Thus, instead of trying to set the parameters of the modules inside the productions, the L-system creates only a generic template at each step. We call this generic template the ideal successor."</span> [p.3](zotero://open-pdf/library/items/JTSK4RXP?page=3)

#important:: [[Important]]  <span class="important">"the setting and the modification of parameters in the L-system modules have been ported to external functions."</span> [p.3](zotero://open-pdf/library/items/JTSK4RXP?page=3)

"globalGoals" [p.3](zotero://open-pdf/library/items/JTSK4RXP?page=3) 

"localConstraints" [p.3](zotero://open-pdf/library/items/JTSK4RXP?page=3) 

"Every time the rules are applied to an existing string of modules, the following actions are executed: • Return the ideal successor by the L-system. The parameters of the modules are unassigned. 
• Call the globalGoals function. This function determines the parameter values of the dominant global goals. All parameter values are set." [p.3](zotero://open-pdf/library/items/JTSK4RXP?page=3) 

#disagreement:: [[Disagreement]]  <span class="disagreement">"Call the localConstraints function. The parameters are checked within the local constraints of the environment.  The parameter values are adjusted to fit these constraints. If this function cannot find suitable parameters, it sets the state flag to FAILED and the module is subsequently deleted."</span> [p.3](zotero://open-pdf/library/items/JTSK4RXP?page=3)


> [!disagreements]+ Disagreement
> #disagreement:: [[Disagreement]] [[Cat]] <span class="disagreement">"So local constraints are only considered all the way at the end. This might be why the result didn't seem to interact with the water features that well. This might mean it won't work well with rivers either."</span> [p.3](zotero://open-pdf/library/items/JTSK4RXP?page=3)
"The roadmap creation tool distinguishes between the following global goals and local constraints. 
• global: street patterns and population density • local: land/water/park boundaries, elevation, crossing of streets" [p.3](zotero://open-pdf/library/items/JTSK4RXP?page=3) 

#important:: [[Important]]  <span class="important">"ω: R(0, initialRuleAttr) ?I(initRoadAttr, UNASSIGNED) p1: R(del, ruleAttr) : del<0 → ε p2: R(del, ruleAttr) > ?I(roadAttr,state) : state==SUCCEED {globalGoals(ruleAttr,roadAttr) creates the parameters for: pDel[0-2], pRuleAttr[0-2], pRoadAttr[0-2]} → +(roadAttr.angle)F(roadAttr.length) B(pDel[1],pRuleAttr[1],pRoadAttr[1]), B(pDel[2],pRuleAttr[2],pRoadAttr[2]), R(pDel[0],pRuleAttr[0]) ?I(pRoadAttr[0],UNASSIGNED) p3: R(del, ruleAttr) > ?I(roadAttr, state) : state==FAILED → ε p4: B(del, ruleAttr, roadAttr) : del>0 → B(del-1, ruleAttr, roadAttr) p5: B(del, ruleAttr, roadAttr) : del==0 → [R(del, ruleAttr)?I(roadAttr, UNASSIGNED)] p6: B(del,ruleAttr,roadAttr) : del<0 → ε p7: R(del,ruleAttr) < ?I(roadAttr,state) : del<0 → ε p8: ?I(roadAttr,state) : state==UNASSIGNED {localConstraints(roadAttr) adjusts the parameters for: state, roadAttr} → ?I(roadAttr, state) p9: ?I(roadAttr,state) : state!=UNASSIGNED → ε"</span> [p.3](zotero://open-pdf/library/items/JTSK4RXP?page=3)

#### Global Goals for road creation
#important:: [[Important]]  <span class="important">"Highways connect centers of population. To find the next population center, every highway road-end shoots a number of rays radially within a preset radius. Along this ray, samples of the population density are taken from the population density map. 
The population at every sample point on the ray is weighted with the inverse distance to the roadend and summed up. The direction with the largest sum is chosen for continuing the growth."</span> [p.3](zotero://open-pdf/library/items/JTSK4RXP?page=3)

#important:: [[Important]]  <span class="important">"On the contrary, streets do not change their direction by following the steepest gradient of the population density map. Typically they follow the dominant street pattern. This is reasonable, since most streets in urban areas are built following a superimposed pattern plan. The created street ends still lower the population density in their environment, usually within the area of the block, according to the mechanisms proposed for Open L-systems [20]. When an area with no population is reached, the streets stop growing."</span> [p.4](zotero://open-pdf/library/items/JTSK4RXP?page=4)

#### Local constraints
#important:: [[Important]]  <span class="important">"The localConstraints function executes the two following steps: • check if the road segment ends inside or crosses an illegal area. 
• search for intersection with other roads or for roads and crossings that are within a specified distance to the segment end."</span> [p.4](zotero://open-pdf/library/items/JTSK4RXP?page=4)

![[temp/img/parishProceduralModelingCities/image-4-x302-y623.png]]
![[temp/img/parishProceduralModelingCities/image-4-x307-y481.png]]
![[temp/img/parishProceduralModelingCities/image-4-x302-y323.png]]
#important:: [[Important]]  <span class="important">"If the first check determines that the road end is inside water, a park or another illegal area, the system tries to readjust the values for the road segment in the following ways. 
• Prune the segment length up to a certain factor so that it fits inside the legal area of the starting point. 
• Rotate the segment within a maximal angle until it is completely inside the legal area. This allows the creation of roads that follow a coastline or a park boundary. 
• Highways are allowed to cross illegal area up to a specified length. The generated highway segment is flagged. At the geometry creation stage it can then be replaced by e.g. a bridge, or two tunnel entrances on both sides."</span> [p.5](zotero://open-pdf/library/items/JTSK4RXP?page=5)

#important:: [[Important]]  <span class="important">"If the localConstraints function finds a street within the given radius of the end of a segment it can modify the parameters for the following events illustrated in figure 8: • two streets intersect → generate a crossing. 
• ends close to an existing crossing → extend street, to reach the crossing. 
• close to intersecting → extend street to form intersection. 
If a crossing is generated, a new node and two edges in the existing street graph have to be created. After a crossing is generated, a road stops growing."</span> [p.5](zotero://open-pdf/library/items/JTSK4RXP?page=5)

![[temp/img/parishProceduralModelingCities/image-5-x48-y256.png]]
![[temp/img/parishProceduralModelingCities/image-5-x305-y471.png]]
#### MODELING OF BUILDINGS
#important:: [[Important]]  <span class="important">"After the creation of highways and streets the populated area of the city is subdivided into many small areas which we call blocks."</span> [p.5](zotero://open-pdf/library/items/JTSK4RXP?page=5)

#disagreement:: [[Disagreement]]  <span class="disagreement">"We assume that most of these allotments are convex and rectangularly shaped. The system therefore forbids the creation of concave allotments."</span> [p.5](zotero://open-pdf/library/items/JTSK4RXP?page=5)

#important:: [[Important]]  <span class="important">"A block is divided into smaller units using a simple, recursive algorithm that divides the longest edges that are approximately parallel until the the subdivided lots are under a threshold area specified by the user"</span> [p.5](zotero://open-pdf/library/items/JTSK4RXP?page=5)

"the user can control the maximum height of a building through the usage of an image map" [p.5](zotero://open-pdf/library/items/JTSK4RXP?page=5) 

![[temp/img/parishProceduralModelingCities/image-5-x304-y124.png]]
![[temp/img/parishProceduralModelingCities/image-6-x47-y495.png]]
.
## Data
> [!footer]+
> 
> 
> > [!important]-
> > ```dataview
> > Table rows.important as ""
> > where file.name = this.file.name
> > group by tag
> > ```
> 
> 
> > [!ideas]-
> > ```dataview
> > Table rows.idea as ""
> > where file.name = this.file.name
> > group by tag
> > ```
> 
> 
> > [!disagreements]-
> > ```dataview
> > Table rows.disagreement as ""
> > where file.name = this.file.name
> > group by tag
> > ```
> 
> 
> > [!confusion]-
> > ```dataview
> > Table rows.confusion as ""
> > where file.name = this.file.name
> > group by tag
> > ```
> 
> 
> > [!critiques]-
> > ```dataview
> > Table rows.critique as ""
> > where file.name = this.file.name
> > group by tag
> > ```
> 
> 
> > [!arguments]-
> > ```dataview
> > Table rows.argument as ""
> > where file.name = this.file.name
> > group by tag
> > ```
> 
> 
> > [!reading]-
> >```tasks
> > not done
> > (description includes todo) OR (description includes researchprompt)
> > filename includes parishProceduralModelingCities
> > ```