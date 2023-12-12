# Agent based generation idea
#type/idea 

First, you calculate all kinds of statistics (road network, blocks, etc.)
Then, you design agent based generators for all steps that have the aim to meet these statistics. For every new road segment that get's generated it decides what to do based on what it means for getting to those statistics. 
There will also have to be certain limits in place to prevent unrealistic generation, like angle constraints, maximum number of connection constraints etc.