---
aliases: ["Yap et al. (2023) A Global Feature-Rich Network Dataset of Cities and Dashboard for Comprehensive Urban Analyses"]
tags: [districts, plots, poi, roads, type/utility, type/data]
year: 2023
---
# A Global Feature-Rich Network Dataset of Cities and Dashboard for Comprehensive Urban Analyses [📖](zotero://select/library/items/Y889UC9Q)

> [!abstract]-
> 
> Urban network analytics has become an essential tool for understanding and modeling the intricate complexity of cities. We introduce the Urbanity data repository to nurture this growing research field, offering a comprehensive, open spatial network resource spanning 50 major cities in 29 countries worldwide. Our workflow enhances OpenStreetMap networks with 40 + high-resolution indicators from open global sources such as street view imagery, building morphology, urban population, and points of interest, catering to a diverse range of applications across multiple fields. We extract streetscape semantic features from more than four million street view images using computer vision. The dataset’s strength lies in its thorough processing and validation at every stage, ensuring data quality and consistency through automated and manual checks. Accompanying the dataset is an interactive, web-based dashboard we developed which facilitates data access to even non-technical stakeholders. Urbanity aids various GeoAI and city comparative analyses, underscoring the growing importance of urban network analytics research.
> 

> [!quote]- Citations
> 
> ```query
> content: "@yapGlobalFeatureRichNetwork2023" -file:@yapGlobalFeatureRichNetwork2023
> ```

%% begin notes %%
## Permanent notes
importance::extreme
completed::false
### Initial thoughts:
- Dataset that combines data from many sources into a ==network== of edges and nodes.
- Not only offers combined data, but is thoroughly checked for quality
- Also has a Python tool "Urbanity" to request data of any place?
- ~ What things are available exactly? Both in their own datasets and the ones downloadable with the tool. 
	- Seems to have:
		- footprint statistics per street + amount of buildings
		- population statistics per street
		- general building function count per street (commercial, healthcare etc.)
- & The `ubanity.building` module has functions to get footprints from Overture and OSM
- & The tool can be used to download both network and footprint data from anywhere!
- & It seems to combine data from many sources. It can for example merge OSM and Overture building footprints

### Relations:
- Uses:
	- [[boeingOSMnx2023]] 
	- [[OpenStreetMap]]
	- [[mapsOvertureMapsFoundation]]

### Summary


%% end notes %%
## Reading notes
%% begin annotations %%

%% end annotations %%



%% Import Date: 2023-12-07T14:17:40.004+01:00 %%
