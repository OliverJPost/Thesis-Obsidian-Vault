---
aliases: ["Barett (2007) L-Systems Considered Harmful"]
tags: [✅, 🔹, roads, step/generation, type/reference]
year: 2007
---
# L-Systems Considered Harmful [📖](zotero://select/library/items/6Q5V5ILN)

> [!abstract]-
> 

> [!abstract]- Related Zotero items (1):  
>
> | title | proxy note | desktopURI |
> | --- | --- | --- |
> | Procedural Modeling of Cities | [[@parishProceduralModelingCities]] | [Zotero Link](zotero://select/library/items/5MKQ3FXP) |  |

> [!quote]- Citations
> 
> ```query
> content: "@barettLSystemsConsideredHarmful2007" -file:@barettLSystemsConsideredHarmful2007
> ```

%% begin notes %%
thumb::![[CleanShot 2023-12-16 at 13.50.49@2x.png]]
## Permanent notes
### Initial thoughts:
- Proposes a better algorithm based on [[parishProceduralModelingCities]]

### Relations:
- [[parishProceduralModelingCities]]

### Summary
Makes the L-system into an algorithm that is actually easy to read and understandable. Original L-system takes ages to understand, and I don't understand why they use strings and string formatting in the first place. Author also claims his implementation is much faster than the original, but I don't see exactly where the speed is increased a lot. The author already admits that the `localConstraints` and `globalGoals` functions are probably the speed bottleneck anyway, and this post doesn't change those at all.

Final algorithm:
```pseudocode
initialize priority queue Q with a single entry:
     r(0,ra,qa)

initialize segment list S to empty

until Q is empty
    pop smallest r(t,ra,qa) from Q
        compute (nqa, state) = localConstraints(qa)
        if (state == SUCCEED) {
            add segment(ra) to S
            addZeroToThreeRoadsUsingGlobalGoals(Q, t+1, qa,ra)
```

%% end notes %%
## Reading notes
%% begin annotations %%

%% end annotations %%



%% Import Date: 2024-05-01T00:52:42.394+02:00 %%
