[[_Generation MOC]]
# Grid generation

#### Ideas
- Use [[Agent based simulation]]
	- Pros:
		- Each class could be an agent. Especially well suited for land use
		- Existing sources for agent based landuse modeling
		- Can clearly encode rules
		- Can take local context into account
	- Cons:
		* Outcomes unpredictable and highly sensitive to input data
		* Difficult to implement
		* Computationally expensive
		* Rules might be arbitrary
- Use [[Generative Adversarial Network (GAN)]]
	- Pros:
		* Works very well for complex patterns
		* Takes spatial relationships into account
	- Cons:
		* Difficult to implement
		* Computationally (RAM) expensive?
		* Black box (AI), not reproducible
- Optimalisation ([[Simulated Annealing]])
	- Pros:
		- Can target specific requirements like adjacency and shape using cost function
		- Can specify exact amount of cells per type
		- Can still be based on parameters like distance to water, distance to city center, terrain, eventually distance to roads
		- Reproducible with seed?
	- Cons:
		- Computationally expensive 
		- Difficult to implement
- Classification ([[Random forest classification]])
	- Pros:
		- Can be trained on worldwide city dataset, while still taking parameters of local context into account
		  - Can fall back on country or region patterns
		- Based on parameters like distance to water, distance to city center, terrain, eventually distance to roads
		- Supposedly easy to implement
	- Cons:
		- Does not take shape and adjacency into account, cannot target specific patch shapes
		- Cannot produce a specific amount of cells of given type