# How it works ?

In order to generate a game map, we have to generate :
- Terrain elevation model (terrain mesh)
- Ground textures
  - Detail textures (id map)
  - Large scale texture (sat map)
- Objets above the ground

The process starts by generating a simplified data model from OpenStreetMap.

Terrain elevation model is generated from SRTM data (wich have a low resoltion), then improved with details from simplified OpenStreetMap data (lakes, roads, buildings, sports area, etc.).

Ground detail textures are generated from simplified OpenStreetMap data.

Large scale texture is generated from Sentinel-2 cloudless data (wich have a low resoltion), then improved from ground detail textures (to reduce color rendering gap).

Objets are placed in areas from simplified OpenStreetMap data.
