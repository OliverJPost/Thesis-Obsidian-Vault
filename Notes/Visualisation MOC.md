# Visualisation

#### Ideas
- Debug view of the generation results where you can click on the elements to see their debug info and go back in generation ticks to see what happens and why
- Rust based backend on Tauri frontend (JS) will enable fast computation and easy 2D and 3D views and user interaction and possibly compilation to WASM and full client side web interface
- Inspector view for the city analysis results from [[Complete analysis pipeline diagram\/plan]] where you have either a list view or a world map view with all the cities that have been analyzed
  - Click on them to see a vector map of the grid analysis result (aggregated into zones)
  - Set of plots to show data distribution (world level, region level, country level, city level, quarter level)
- Node-like view of the generation steps where a plug-in system could be used for swapping the different generators with different/new ones