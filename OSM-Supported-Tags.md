# OpenStreetMap Supported Tags

GameRealisticMap uses a simplified data model built from OSM data. 

This document list all supported OSM data tags and their simplification in GameRealisticMap .

## Surfaces

![Area](https://wiki.openstreetmap.org/w/images/thumb/e/e6/Osm_element_area.svg/30px-Osm_element_area.svg.png) Only these elements mapped as areas are detected.

| iD Title (en-US) | Detected OSM Tags                             | GRM interpretation |
|------------------|-----------------------------------------------|--------------------|
| Vineyard         | `landuse=vineyard`                            | Vineyard  |
| Orchard          | `landuse=orchard`                             | Orchard   |
| Farmland (grass) | `landuse=farmland` `crop=grass`               | Meadow    |
| Farmland         | `landuse=farmland` (others)                   | Farmland  |
| Meadow           | `landuse=meadow`                              | Meadow    |
| Meadow           | `natural=meadow`                              | Meadow    |
| Grassland        | `natural=grassland`                           | Meadow    |
| Heath            | `natural=heath`                               | Meadow    |
| Sand             | `natural=sand`                                | Sand      | 
| Beach            | `natural=beach`                               | Sand      |
| Sand surface     | `surface=sand`                                | Sand      |
| Managed Forest   | `landuse=forest`                              | Forest    |
| Natural Wood     | `natural=wood`                                | Forest    |
| Bare Rock        | `natural=bare_rock`                           | Rocks     |
| Scrub            | `natural=scrub`                               | Scrubs    |
| Lake             | `water=lake`                                  | Lake      |
| Pond             | `water=pond`                                  | Lake      |
| Water            | `natural=water`                               | Lake      |

## Individual trees and tree rows

![Node](https://wiki.openstreetmap.org/w/images/thumb/7/76/Osm_element_node.svg/30px-Osm_element_node.svg.png) Only these elements mapped as nodes are detected.

| iD Title (en-US) | Detected OSM Tags          | GRM interpretation |
|------------------|----------------------------|--------------------|
| Tree             | `natural=tree`             | Individual tree |

![Way](https://wiki.openstreetmap.org/w/images/thumb/e/ee/Osm_element_way.svg/30px-Osm_element_way.svg.png) Only these elements mapped as paths are detected.

| iD Title (en-US) | Detected OSM Tags          | GRM interpretation |
|------------------|----------------------------|--------------------|
| Tree Row         | `natural=tree_row`         | Tree row |

## Barriers : fences, hedges, walls

![Way](https://wiki.openstreetmap.org/w/images/thumb/e/ee/Osm_element_way.svg/30px-Osm_element_way.svg.png) Only these elements mapped as paths are detected.

| iD Title (en-US) | Detected OSM Tags                             | GRM interpretation |
|------------------|-----------------------------------------------|--------------------|
| Wall             | `barrier=wall`                                | Wall               |
| Fence            | `barrier=fence`                               | Fence              |
| Hedge            | `barrier=hedge`                               | Hedge              |

## Buildings and assimilated

![Area](https://wiki.openstreetmap.org/w/images/thumb/e/e6/Osm_element_area.svg/30px-Osm_element_area.svg.png) Only these elements mapped as areas.

![Node](https://wiki.openstreetmap.org/w/images/thumb/7/76/Osm_element_node.svg/30px-Osm_element_node.svg.png) Beta 7 will add support for those elements mapped as node.

| iD Title (en-US) | Detected OSM Tags                             | GRM interpretation |
|------------------|-----------------------------------------------|--------------------|
| ? | `building=*` `shelter_type=public_transport`  | Bus Stop Shelter |
| ? | `building=*` `tower:type=communication`     | Radio Tower |
| ? | `building=church`                           | Church |
| ? | `building=hut`                              | Hut |
| ? | `building=shed` `public_transport=platform` | Bus Stop Shelter |
| ? | `building=shed` (others)                    | Shed |
| ? | `building=commercial`                       | Commercial |
| ? | `building=retail`                           | Retail |
| ? | `building=farm_auxiliary`                   | Agricultural |
| ? | `building=barn`                             | Agricultural |
| ? | `building=owshed`                           | Agricultural |
| ? | `building=water_tower`                      | Water Tower |
| ? | `building=garage`                           | Individual Garage |
| ? | `building=house` (Beta 7)                   | Residential |
| ? | `building=detached` (Beta 7)                | Residential |
| ? | `building=semidetached_house` (Beta 7)      | Residential |
| ? | `building=farm` (Beta 7)                    | Residential |
| ? | `building=*` `historic=fort`                | Historical Fort |
| ? | `building=*` `brand=*`                      | Retail |
| ? | `man_made=lighthouse` (Beta 7)              | Lighthouse |
| ? | `man_made=water_tower` (Beta 7)             | Water Tower |

## Urban areas

![Area](https://wiki.openstreetmap.org/w/images/thumb/e/e6/Osm_element_area.svg/30px-Osm_element_area.svg.png) GRM prefers those elements as areas when allowed by OSM conventions.

Urban areas are used for specific ground texture, filling elements, and default building type.

| iD Title (en-US) | Detected OSM Tags      | GRM interpretation (default building type) |
|------------------|------------------------|--------------------|
| Industrial Area  | `landuse=industrial`   | Industrial |
| Commercial Area  | `landuse=commercial`   | Commercial|
| Residential Area | `landuse=residential`  | Residential |
| Retail Area      | `landuse=retail`       | Retail |
| Military Area    | `landuse=military`     | Military |
| Farmyard         | `landuse=farmyard`     | Agricultural |

## Roads

![Way](https://wiki.openstreetmap.org/w/images/thumb/e/ee/Osm_element_way.svg/30px-Osm_element_way.svg.png) Only these elements mapped as paths are detected.

| iD Title (en-US) | Detected OSM Tags                             | GRM interpretation |
|------------------|-----------------------------------------------|--------------------|
| ? | `highway=motorway`                      | Two Lanes Motorway |
| ? | `highway=primary`                       | Two Lanes Primary Road |
| ? | `highway=primary_link`                  | Two Lanes Primary Road |
| ? | `highway=trunk`                         | Two Lanes Primary Road |
| ? | `highway=trunk_link`                    | Two Lanes Primary Road |
| ? | `highway=motorway_link`                 | Two Lanes Primary Road |
| ? | `highway=secondary`                     | Two Lanes Secondary Road |
| ? | `highway=seconday_link`                 | Two Lanes Secondary Road |
| ? | `highway=tertiary`                      | Two Lanes Secondary Road |
| ? | `highway=tertiary_link`                 | Two Lanes Secondary Road |
| ? | `highway=road`                          | Two Lanes Secondary Road |
| ? | `highway=living_street`                 | Two Lanes Urban Road |
| ? | `highway=residential`                   | Two Lanes Urban Road |
| ? | `highway=unclassified`                  | Two Lanes Urban Road |
| ? | `highway=service` [1]                   | One Lane Urban Road |
| ? | `highway=footway` [2]                   | Urban footway |
| ? | `highway=track`                         | Path road |
| ? | `highway=pedestrian` `surface=asphalt`  | Urban footway |
| ? | `highway=pedestrian` `surface=paved`    | Urban footway |
| ? | `highway=pedestrian` (others)           | Trail |

[1] For optimization purpose, some service roads are ignored :
- `access=private` are ignored
- `service=driveway` with restrictions are ignored

[2] Sidewalks and crossing are ignored, they are always procedural to ease adjusting to in-game road size

## Objects

![Node](https://wiki.openstreetmap.org/w/images/thumb/7/76/Osm_element_node.svg/30px-Osm_element_node.svg.png) Only these elements mapped as nodes are detected.

| iD Title (en-US) | Detected OSM Tags                             | GRM interpretation |
|------------------|-----------------------------------------------|--------------------|
| ? | `amenity=bench`                                      | Bench |
| ? | `amenity=waste_basket`                               | Basket |
| ? | `amenity=post_box`                                   | PostBox |
| ? | `amenity=recycling` `recycling_type=container`       | Recycling Container |
| ? | `man_made=water_well`                                | Water Well |
| ? | `man_made=flagpole` (Beta 7)                         | Flagpole |
| ? | `leisure=picnic_table`                               | Picnic Table |
| ? | `emergency=fire_hydrant` `fire_hydrant:type=pillar`  | Fire Hydrant |
| ? | `information=board`                                  | Information Board |
| ? | `historic=wayside_cross`                             | Wayside Cross  |
| ? | `historic=memorial` `memorial=statue`                | Statue |
| ? | `historic=memorial` `memorial=war_memorial`          | War Memorial |
| ? | `artwork_type=sculpture`                             | Sculpture |
| ? | `highway=street_lamp` (Beta 7) [1]                   | Street Lamp |

[1] Street lamps mapped are preferred, even if procedural street lamps is enabled.

## Railways

![Way](https://wiki.openstreetmap.org/w/images/thumb/e/ee/Osm_element_way.svg/30px-Osm_element_way.svg.png) Only these elements mapped as paths are detected.

| iD Title (en-US) | Detected OSM Tags           | GRM interpretation |
|------------------|-----------------------------|--------------------|
| Train Track      | `railway=rail`              | Railway |
| Disused Railway  | `railway=disused` (Beta 7)  | Railway |

![Node](https://wiki.openstreetmap.org/w/images/thumb/7/76/Osm_element_node.svg/30px-Osm_element_node.svg.png) Only these elements mapped as nodes are detected.

| iD Title (en-US)      | Detected OSM Tags         | GRM interpretation |
|-----------------------|---------------------------|--------------------|
| Railway-Road Crossing | `railway=level_crossing`  | Railway crossing with a road |

