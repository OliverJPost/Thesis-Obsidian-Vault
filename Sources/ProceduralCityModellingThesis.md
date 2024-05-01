---
aliases: [" download.pdf"]
tags: [✅, 💎, buildings, districts, plots, roads, step/generation, type/reference]
year: 
---
# download.pdf [📖](zotero://select/library/items/3JE22TXE)

> [!abstract]-
> 

> [!quote]- Citations
> 
> ```query
> content: "@ProceduralCityModellingThesis" -file:@ProceduralCityModellingThesis
> ```

%% begin notes %%
thumb::![[Pasted image 20231210234540.png]]
## Permanent notes
### Initial thoughts:
- Road networks look promising
- Code available (runs in Unreal Engine)
- Goes all the way to generating furniture

### Relations:
- Implements [[barettLSystemsConsideredHarmful2007]] variation of [[parishProceduralModelingCities]]

### Summary
Implements the Parish & Mueller L-Systems, and has code! Results look better than [[hoofYatoomCitygenerator2022]]. Report itself doesn't describe much, except that it uses a noise map.

%% end notes %%
## Reading notes
%% begin annotations %%

Imported on 2023-12-17 19:41



- @ Using a priority queue, whenever a road is placed, the potential extensions of that road are placed as well, each given a priority1 depending on the determined value of the road, (to see how this value is calculated see 4.2). Whenever a road is actually placed it might also need fitting to attach with other existing roads. [(p. 26)](zotero://open-pdf/library/items/LBKL3XYI?page=26&annotation=4D6DE5DM) 
- @ Using this technique the main road is given slightly higher priority, and smaller roads are given lower, meaning main city roads are placed before the smaller ones. This makes the small roads adapt to the larger roads instead of vice versa, creating a more natural looking road network. [(p. 26)](zotero://open-pdf/library/items/LBKL3XYI?page=26&annotation=MGWXJZS7) 
- @ In addition to this general heatmap, this project uses a ”negative” heatmap that is relevant for the area covered by main roads. Basically, when a large road is placed, each new large road within a certain distance will have lower priority than they would otherwise have. This attempts to make sure that the main roads do not go around in circles around certain points. It also artificially emulates the reduced need of a main road close to an area where there already is one close by. [(p. 26)](zotero://open-pdf/library/items/LBKL3XYI?page=26&annotation=QV7T6C8R) 
- & based on the improved version [3] of Parish and M¨uller’s work[1] [(p. 33)](zotero://open-pdf/library/items/LBKL3XYI?page=33&annotation=3SIH855D) 
- @ When placed, a road attempts to place a new road piece in front and some attempt to place road pieces perpendicular to itself. The exact angles of these roads are calculated by testing which directions yields the best priority, within a defined maximum angle. For a certain maximum change intensity a road forward could have a rotation anywhere between previous segment− maximum change intensity and previous segment+maximum change intensity. This means that higher values for maximum change intensity yields more curves and a value of 0 gives a strict grid network. [(p. 33)](zotero://open-pdf/library/items/LBKL3XYI?page=33&annotation=VENMXLYW) 

- @ ****  [(p. 34)](zotero://open-pdf/library/items/LBKL3XYI?page=34&annotation=JN4G9M28) ![[_Vault/_Attachments/image-34-x49-y527.png]]





%% end annotations %%



%% Import Date: 2024-05-01T00:52:43.343+02:00 %%
