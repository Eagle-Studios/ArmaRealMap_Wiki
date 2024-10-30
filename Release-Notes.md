[Version française](Release-Notes-FR)

# Release Notes

## Beta 10 / Version 0.10

Available since 2024-06-04

### Summary
- NEW : Non uniform density for object placement
- NEW : Ground Detail Texture Library
- NEW : Satellite color correction option
- NEW : Recent files list
- NEW : "Aerial image" view in map editor and composition editor
- NEW : Edit ground textures of an existing map
- NEW : Save a map to a new location (wrp file) : allow to change pbo prefix/world name
- NEW : Aeroways (flattening and surface)
- NEW : Asphalt surface
- NEW : Terrace are detected as Residential buildings
- NEW : Randomization operations within composition to have less uniforms renders (Pre-configured on Vineyards).
- NEW : You can change the data sources URI to use mirrors or custom compatible sources
- FIXED: Cowshed are now correctly detected as Agricultural buildings.
- FIXED: Error preventing generation of locations with partial SRTM coverage
- FIXED: Out of bound elevation was sometime not compatible with border elevation leading to gaps
- TWEAKED: Errors caused by corrupted p3d file now indicates the file name 

### Non uniform density

Non uniform density allows to make large areas create less uniform.

In the area settings, click on the pen after overall density parameters:
![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/c9f72a7e-e6a3-4275-8b1b-e43fb3297a0e)

Then tune settings to have the wanted density pattern
![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/5a099a56-bdd2-4953-8181-93f9490044d5)

The underlying algorithm is powered by [FastNoiseLite](https://github.com/Auburn/FastNoiseLite).

## Ground Detail Texture Library

The new Ground Detail Texture Library allows you to access existing game-provided ground textures.

![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/63cc7f06-178c-4b87-b4d0-5c500df68210)

It also allows you to import external ground textures.

![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/68f8a15c-09fd-4ee5-a4ab-6df9d95d5bb6)

For custom ground textures, you can customize clutter. You have do drag-and-drop from object browser.

![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/f77b9e1b-3e9f-45c3-bd8b-e4607198521b)

### Edit ground textures of an existing map

You can mass replace ground textures of an existing map.

Please note that import/export of texture mask image now uses colors codes from the Ground Detail Texture Library. It means that you can import an image with any texture of the library to add it to an existing map.

![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/e1e3aa75-086b-4821-a60b-ad3fec1883f1)

### Randomization operations within composition

Randomization operations allows to create less uniform worlds.

It can be added on any composition, click on "Edit" of the item.

![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/36c4e9a5-b361-4977-90ad-c492d93c54a4)

In the "Objects position" tool window, select an item in the bottom list.

Below the item a form will appear to allow you to set randomization. 

![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/c509c805-f985-414c-bb1e-2f3b9a25bfd4)

### Updgrade maps generated with previous versions

If you use edit ground texture of an existing maps, you need to update the existing config.cpp to include additionals includes:
- In the CfgWorlds entry 
  - define `class DefaultClutter;`
  - define `class clutter` and include `clutter.hpp`
- at the end of the file include `surfaces.hpp`

```cpp
// ...
class CfgWorlds
{
    class baseworld;
    class worldname : baseworld
    {
        // ...
        class DefaultClutter;
        class clutter {
            #include "clutter.hpp"
        };
        // ...
    };
};
#include "surfaces.hpp"
```

## Beta 9 / Version 0.9

Available since 2023-11-28

### Summary

- NEW: Road editor for Arma 3 map files
- NEW: 3D Preview in asset browser
- NEW: Mass edit operation on objects of an Arma 3 map file
- NEW: Import/Export elevation grid of an Arma 3 map file
- FIXED: Opening an Arma 3 map file after a binarize related crash now restore config allowing further edit.
- TWEAKED: Scrolling in preview map now use the right button of the mouse

### Road editor for Arma 3 map file 

The first feature to integrate the map editor is the modification of the roads of an Arma 3 map. The editor will become a full featured map editor in the future. The editing process will not be limited to Arma 3 maps, but will allow also to edit OSM interpreted data.

Use the Open Editor button

![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/8373ea1a-5891-48a8-a37e-929ed5323288)

You can select roads, move points, add points (double click on road), continue paths, or merge them (use ctrl+click to select multiple roads).

![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/a066b50c-b5e4-4c10-a50a-da4466b426f2)
![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/1b31e3bc-3ecf-45c0-8d76-de58a9a9b0d7)

In the Inspector tool you can change road type.

![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/cada9f1c-f18d-41ba-8d6f-7800773c0974)
![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/59e5b7b2-18dd-4e1f-a42d-5ddeadde496e)

You can also add roads.

![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/4526815d-aa32-482c-b048-abe6efaa59bd)

Note: Depending on Zoom level more or less objects shapes will appear. They cannot be edited yet.

### 3D Preview in asset browser

Some objects does not feature a screen shot, use right click to get a 3D preview.

![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/54018ab8-87b7-4252-9e02-e54f708179db)

Use right-click to rotate object, and mouse wheel to zoom in/out.

![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/3aa4e811-e92a-4f57-b0de-0376ac057187)

The preview is really basic, color render can be very different from actual in-game appearance.

### Mass edit operation on objects of an Arma 3 map file

A new "objects" section is available with a list of all used objects.

![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/cb4050d7-1d30-4d34-859c-6929eb954129)

You can use "Replace", to replace an object by an other (Use Entrer to add a line).

![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/dab8d7d1-ed82-4d8e-8ee9-2385c77ed133)

You can use "Reduce", to reduce the number of objects (Use Entrer to add a line).

![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/043755ba-3070-47ec-865d-9d39fbe4afe2)

### Import/Export elevation of an Arma 3 map file

A new "Elevation" section is available to import or export elevation data.

![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/2aec3d61-fef5-4271-91c1-7e71101137f3)

## Beta 8 / Version 0.8

Available since 2029-10-24

### Summary

- NEW: Tagging support on variations, seeds, and filling objects
- NEW: Support for glacier and scree grounds
- NEW: ACE3 Weather settings
- NEW: Configuration of out of bounds procedural generation 
- NEW: Randomization of procedural street lights distance
- NEW: Support for wind turbines
- FIXED: Empty variations and seeds are ignored to balance probabilities when saving an asset configuration. This avoid the "Sum of probability must be 1" error.
- FIXED: Hemisphere of generated map was reverted. For northern hemisphere map sun was appearing at North, and daylight duration was incorrect.
- FIXED: Dark theme
- TWEAKED: Street lights are no more generated within ocean (with CentralEurope preset)

### Tagging support on variations, seeds, and filling objects

You can now add conditions on variations (filling, edged, fences, walls). Available tags are quite limited but will be extended in future versions.

Please note that conditions is evaluated on each variations, all variations that matches can be used based on specified probabilities. If two variations are designed to be exclusive, you have to exclusive conditions on them. For exemple one with `IsMilitary` and the other one with `!IsMilitary`.

![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/1f43db87-3454-402c-a46b-c970dafecf78)

You can also add conditions on seeds and objects within filling variations.

### Glacier and scree grounds

Areas that are mapped as Glacier and Scree have now a specific ground texture. Scree allows also to have specific filling objects.

### ACE3 Weather settings

Generated maps now includes data required by [ACE3 Weather](https://ace3.acemod.org/wiki/feature/weather) module to generate realistic weather (Temperature, humidity and wind).

Data is based on statistics on ERA5 data from years 2010 to 2020.

This feature is available as a standalone service on https://arm.pmad.net/AceWeather

Existing maps, must edit their config.cpp file to benefit from this change as this file is never overwritten. You have to add `#include"ace-weather.hpp"` just after `#include"mapinfos.hpp"`

### Wind turbines

Mapped Wind turbines are now generated. They are oriented according to dominant wind (based on statistics on ERA5 data from years 2010 to 2020).

![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/e6be344d-cc7b-4866-80ae-802956a698d5)

### Out of bounds procedural generation

Generated configuration now includes procedural terrain generation (feature introduced by Arma 3 v2.04). This avoids full flat terrain around the map.

![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/760ef785-a09a-4c4e-adca-ea8c78104225)

## Beta 7 / Version 0.7

Available since 2029-09-18

### Summary

- NEW: Support for streetlights
- NEW: Support for sidewalks
- NEW: Support for flagpole
- NEW: Support for lighthouses
- NEW: Support for "non-building" water towers
- NEW: Studio integrated preview of interpreted OpenStreetMap data
- NEW: Integrate objects into map from a TerrainBuilder text file
- NEW: Export/import satellite image and texture mask to edit them
- NEW: Default filling option for urban areas
- NEW: Some objects can now have tags to create conditions on where they should be used
- FIXED: Road’s indexing was incorrect leading to misc. issues like building largely overlapping roads
- FIXED: Ocean boundary resolution was sometime incorrect, leading to "under-water" maps
- TWEAKED: Buildings tagged as houses in OpenStreetMap are now always residential buildings
- TWEAKED: Small bridges are now ignored as they can't be correctly generated

### Streetlights and sidewalks

Streetlights are now generated. OpenStreetMap data is completed by a procedural generator, as most streetlights are not mapped. Procedural generator settings are available on each road type in the asset configuration.

Sidewalks are also generated, but does not rely on OpenStreetMap data. It uses a specific procedural generator. Its settings are available on each road type in the asset configuration. 

Warning: The sidewalks gives mixed results, you might prefer disable it by changing the setting on each road type, or removing the sidewalk asset. This will be reworked in a future release.

![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/ee7bec33-a9f4-4416-98e1-3bdcdb5090c5)

### New buildings and objects

| Lighthouse | Flagpole | Water tower |
|------------|----------|-------------|
| ![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/e4146701-24e2-48d8-8c5e-99c6e3ec1563) | ![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/958a2c08-c177-491e-811e-3b6f9a19d95d) | ![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/fe0178b8-ce38-4cdf-bf27-60f202ed3a7a) |

### Integrated preview

Interpreted data from OpenStreetMap can now be previewed in a built-in tool. This allows to pick specific layers and avoid the compute time of other layers.

It gives you a quick access to the viewed area on OpenStreetMap.org to check source data and eventually fix it.

Warning: Contour lines can be really long to compute.

![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/b93ff337-dee6-449d-aa81-1031ff573e14)

### Default filling

You can now specify objects to use to fill urban areas, to make those areas more lively.

### Import Terrain Builder text files

The map editor allows you yo import objects from Terrain Builder format text files. This allows you to use tools like [Plopper](https://steamcommunity.com/sharedfiles/filedetails/?id=1687651646).

### Import/Export satellite image and texture mask

The map editor also allows you to export and import satellite image and texture mask. This allows you to rework those images with an external tool such as [Paint.Net](https://www.getpaint.net/), [Gimp](https://www.gimp.org/) or Photoshop.

### Tagging system

Elements from the "Objects" category are the first to benefit from the tagging system. This system allows you to add conditions on where an object can be used.

This system will be progressively made available on all elements in future releases.

![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/d8dd2f2e-7c13-41e5-b50e-e8b71bb88523)

## Beta 6 / Version 0.6

Available since 2023-08-28

### Summary

- NEW: Support for Vineyards, Orchards and tree rows
- NEW: Filling of default areas 
- FIXED: Footsteps where not audible on maps processed with builtin PBO generator
- FIXED: Ocean depth was shifted around 450m north-east
- FIXED: Some areas filling was never ending
- TWEAKED: Export/import from Eden is now done into multiple parts if size exceed Arma 3 limits.
- TWEAKED: Memory usage have been drastically reduced when filling large areas

### Vineyards

Vineyards areas are collected from OpenStreetMap data. In the asset configuration, you can specify the position of rows using composition or individuals objects.

Preview with CentralEurope builtin asset configuration:

![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/d0d2c7b0-80a0-4864-a6d1-0b3091682b9f)

### Orchards 

Orchards areas are collected from OpenStreetMap data:
- Large areas are generated with rows of trees
- Smaller area are generated with randomly placed trees

Preview with CentralEurope builtin asset configuration:

![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/aaede1af-2efe-4d89-a872-15ee9f984db3)

### Tree rows

Tree rows are also collected from OpenStreetMap, and generated with tree rows.

### Default areas

The studio allowed to specify default areas filling objects, but they were not used. Objects are now used to fill "blank" areas.

The CentralEurope asset configuration does not includes default areas. You have to create your own asset configuration to use that feature.

### Very large areas support

Fixes included in this version, allows you to generate large maps with a lot of objects with lower memory requirements. Anyway the processing time remain very long (multiple hours).

![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/a50a1a41-0b65-4e79-a626-2e5b4b5eda03)

### Multiple part Eden export/import

Arma 3 limits to 10 Mo the size of strings. Previous export function may exceed this limit and made the export/import process impossible.

Export size have been optimized to be much more smaller, and is automatically break down into multiple parts if size exceed Arma 3 limits.

![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/02ed5db4-ee24-4063-a4a4-ff8282a86199)


## Beta 5 / Version 0.5 

Available since 2023-08-15

### Summary

- NEW: Edit with Eden Editor
- NEW: Generate a mod from a WRP file
- NEW: Recent generated mods are displayed in the home screen
- TWEAKED: Changed satellite image textures to reduce the grid effect
- TWEAKED: Terrain builder export split large images into smaller images to avoid some performance issues
- TWEAKED: User inputs are validated in map creation
- TWEAKED: Automatic values are displayed in relevant fields
- FIXED: Railroad detection may have crashed application
- FIXED: Error "Attribute id already exists" could occurs on some regions
- FIXED: TML filename was incorrect for some mods

### Edit with Eden Editor

This feature is intend to allow a simpler way of editing generated map.

It can used to fix objects location, add or remove objects. See [Edit With Eden Editor](Edit-With-Eden-Editor).

| Right click and "Edit Object" | Object becomes editable | Move object |
|------------------|-------------------------|---------------|
| ![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/ce60a53a-f42b-4542-8023-53065e27f254) | ![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/a5f3bda7-a787-4535-bc3c-ecdedd662a24) | ![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/811d7e75-1683-4c6c-a8d7-1954da5a6f21) |

It's not as powerful as Terrain Builder editing, but it is much more accessible. See [Edit with Eden editor and integrate to map, or export to Terrain Builder](https://github.com/jetelain/ArmaRealMap/wiki/Create-a-map-for-Arma-3#edit-with-eden-editor-and-integrate-to-map-or-export-to-terrain-builder) for a comparaison of editing processes.

### Home screen

List of recently generated mods (exports to terrain builder are not yet included):

![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/8355f6a8-c95a-4c33-9830-c24ed402f81d)

### Generate mod from a WRP file

You can open a WRP file from the project drive, typically generated with Terrain Builder or with GameRealisticMap, and generate a mod with the builtin generator.

![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/518bf8e7-4105-4f8a-84cf-e3d62f6e5ab8)

Note: In current version, the generator assumes that PNG have been already converted to PAA.

### Satellite image textures

In map generation process a "fake satellite image" is built using colors from terrain texture. This is intend to reduce the color gap between satellite image (used far from the camera) and ground texture (used near the camera).

Textures have been replaced by a solid color to avoid a "grid effect".

![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/7749beab-4eaf-4854-af6d-85b756414998)


## Beta 4 Fix 1 / Version 0.4.1

Available since 2023-08-09

### Summary

- FIXED: Sometime railroad detection crashed the application
- FIXED: Some parts of the map may appeared white due to a missing file 
- FIXED: An error in Performance Counters prevented generation launch, error is now ignored
- FIXED: Most maps with coastline were generated underwater

## Beta 4 / Version 0.4

Available since 2023-08-07

### Summary

- NEW: Railways support (only straight segments)
- NEW: Ocean support (elevation and ground texture)
- NEW: Generate a map to terrain builder file format, to edit the map with classic tools
- NEW: Fences/Walls/Hedges can use randomized segments 
- NEW: Fences/Walls can have corner objects such as columns
- NEW: Hedges can have a natural render using random oriented bushes or small trees
- NEW: World-wide support (including above latitude 60° North and below 60° South using JAXA data)
- NEW: An error report can be generated from the Help menu to ease diagnostics (generate a zip file)
- FIXED: Long bridges now works, they can now be built with more than one middle element
- FIXED: Error popups show the underlying error instead of a generic message
- FIXED: Stripes appeared on some maps due to an internal computation error
- TWEAKED: OpenStreetMap data download timeout have been increased to 5 minutes (instead of 3 minutes and 15 seconds)

### Ocean support 

Ocean/sea is now supported, that allow to create island or coastline maps.

Ocean depth is based on [SRTM15+](https://topex.ucsd.edu/WWW_html/srtm15_plus.html) that includes data from various public domain sources.

Land surface remains based on SRTM1 from NASA for most areas. Regions with no SRTM1 data now use AW3D 30 from JAXA.

Coastline is extracted from OpenStreeMap, to determines whenever land or ocean depth should be used for elevation.

A specific texture is used for ocean ground / sea bed. A sand texture is used for coastline (both water side and land side). Those textures can be changed with a custom asset configuration.

| Preview #1 | Preview #2 |
|-------------------------------|-------------------------------|
| ![ocean2](https://github.com/jetelain/ArmaRealMap/assets/33651126/765e4744-50da-456a-8d24-bc07fefe259c) | ![ocean1](https://github.com/jetelain/ArmaRealMap/assets/33651126/b6bca2eb-4ad5-4ce9-bd33-83dc142e2b62) |


### Terrain Builder Export

You can now generate a map to import it in Terrain Builder, and then edit it with classic tools. 
See [Terrain Builder Export](Terrain-Builder-Export) for more information.

![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/db9ac18e-5be9-4db2-8bf3-7be765bb6b0d)

<img src="https://user-images.githubusercontent.com/33651126/258084294-fcd6b626-1843-4dfe-b0a5-7bd1fe4e4b47.png" alt="terrain builder export" width="75%" />

### Fences/Walls corner

Wall corner (with angle larger than 45°) use to have a poor render due to the gap between objects. Now a corner object have been defined, and can be changed, to hide the gap.

| Beta 3, without corner object | Beta 4, with corner object |
|-------------------------------|-------------------------------|
| ![without corners](https://github.com/jetelain/ArmaRealMap/assets/33651126/95f55dbe-eb65-43fc-9a21-697ac1feea99) | ![with corners](https://github.com/jetelain/ArmaRealMap/assets/33651126/cb2172f5-02ea-4804-af7a-088c7a62a566) |

### Natural hedges

Natural hedge was not possible to achieve in previous version. Now you can set a list of objects that will be placed with random orientation. Anyway, this is not included in a builtin asset configuration, you can use it with our own configurations.

![natural hedge](https://github.com/jetelain/ArmaRealMap/assets/33651126/253f1f2d-3a8d-4903-905a-725642e3aefe)