[Version française](Edit-With-Eden-Editor-FR)

# Introduction

[Eden Editor (also called 3DEN Editor)](https://community.bistudio.com/wiki/Category:Eden_Editor) is the Arma 3 builtin scenario editor. With specific extensions you can use this editor to edit [map generated with GameRealisticMap Studio](Create-a-map-for-Arma-3).

Note: Not all features from Eden Editor can be integrated to the map, many aspects will remain part of the scenario and wont be able to be integrated to the map.

# 1. Launch Arma with required mods

Subscribe to the mod [Export to GameRealisticMap](https://steamcommunity.com/sharedfiles/filedetails/?id=3016661145) on the Steam Workshop.

You may also subscribe to mod that allow access to all objects from eden editor such as:
- [Eden Extended Objects](https://steamcommunity.com/sharedfiles/filedetails/?id=882231372)
- [O&T Expansion Eden](https://steamcommunity.com/sharedfiles/filedetails/?id=1923321700)

To be able to edit terrain elevation, you will also requires the [Deformer](https://steamcommunity.com/sharedfiles/filedetails/?id=2822758266) mod.

To launch Arma 3 to edit your map, you can either use GameRealisticMap Studio or Arma 3 Launcher.

## With GameRealisticMap Studio
- From the home screen choose your map from recent list
- Click on button "Import changes from Eden Editor"
- Click on button "Launch Arma 3". The previous mods will be automatically activated if installed.

| Home Screen | Import from Eden button | Launch Arma 3 |
|----------|----------|----------|
| ![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/a7363c45-d7af-401f-965f-fa233d5a63cd) | ![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/bd4d09b7-7c6f-4659-81bf-4c8fce87a797) | ![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/bb91d459-45bf-4551-8545-e5ed5849bfbb) |

##  With Arma 3 Launcher
- Choose the preset that have been generated for your map
- Activate the mods
  - CBA_A3
  - Export to GameRealisticMap
  - All additional mods 
- Launch Arma 3

| Choose preset | Activate mods | Launch Arma |
|---------------|-------------|-------------|
| ![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/7ed0c63e-dd52-4448-be33-240d4ff60237) | ![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/2cccf602-44ef-4be4-8f01-64264c936400) | ![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/0e0a4fac-ea3f-453d-bd40-b3b9aaf2df3b) |

# 2. Edit with Eden Editor

## Add objects

Add objects on the map the regular way.

Please note: Not all objects can be integrated into the map. The export process will filter automatically objects: non exportable objects will be ignored. 

## Remove objects

You can use this modules to remove objects:
- Edit Terrain Object, and select Hide status : hide/remove a specific object
- Hide Terrain Objects : hide/remove all objects within an area

![Modules list](https://github.com/jetelain/ArmaRealMap/assets/33651126/6a7bd343-3803-4642-881b-5729d27f3c7b)

## Edit objects

Right click on the center of the object, then choose "Edit Object". Object will removed using a "Edit Terrain Object" and an editable object will replace it.

| Right click and "Edit Object" | Object becomes editable | Move object |
|------------------|-------------------------|---------------|
| ![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/ce60a53a-f42b-4542-8023-53065e27f254) | ![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/a5f3bda7-a787-4535-bc3c-ecdedd662a24) | ![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/811d7e75-1683-4c6c-a8d7-1954da5a6f21) |

It might not apply to correct object, remove module and object and try an other location.

If it does not work, use instead a Edit Terrain Object module. Once you have placed the module on the correct object,  right click on the module, then click on "Recreate hidden objects".

## Deform the terrain

Use Deformer to change terrain.

Warning: Do not use the static terrain objects converter from Deformer. It's not intentionally supported by the export extension, and will cause major issues if the revision of the map mismatch. Deformer use ObjectID from the map that will change at each time the map is edited.

# 3. Export data

In Eden Editor, in the Tool menu, click on "Export to GameRealisticMap Studio".

![Tool Menu](https://github.com/jetelain/ArmaRealMap/assets/33651126/07bf49a9-a080-438f-9260-5f2ed780c736)

All export data will be copied to the clipboard. You may want to save it to a text file with a tool like notepad or notepad++ to have a backup.

Objects that can be integrated are automatically moved to a new layer named "Integrable to map (to remove)". All other objects cannot be integrated.

# 4. Import changes in GameRealisticMap Studio

If you have started Arma 3 with GameRealisticMap Studio, go back to GameRealisticMap Studio and click on "Refresh" button.

Otherwise, launch GameRealisticMap Studio, choose your map from the recent maps, and then click on "Import changes from Eden Editor".

![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/1855670c-82f0-426d-b275-8531353a3353)

Check if everything is OK, then click on "Import from clipboard", then save the file.

Note:
- Ensure that Arma 3 is closed, it locks mod files and will make mod generation fail.
- Ensure to enable all mods you used for mapping in GameRealisticMap Studio settings otherwise you will have a "file not found error".

Click on "Generate a mod for Arma 3" to re-generate the mod.

# Something went wrong ?

If editing went wrong, you can easily get back to a previous version of the map with the "File history". On the previous version, click on "Restore", then Save the file, and click again on "Generate a mod for Arma 3". Last 10 saved versions are kept to revert any wrong edit.

![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/15e65175-6d96-49a7-a056-769aadb87580)

If you have used plopper or paint to define a new surface (and you have ensured these surfaces are present in CfgSurfaces & CfgLayers) but you are still unsure of why your surface might not be working?
I would suggest using this great guide/script that identify most issues arising from Surfaces and Clutter: https://gist.github.com/pennyworth12345/6670b948f2cde80d28ad01ebd584db1c
