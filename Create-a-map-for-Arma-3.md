[Version française](Create-a-map-for-Arma-3-FR)

Please ensure that you have [installed all required tools](Install-required-tools-for-Arma-3) before starting; It is VITAL that you have followed the installation procedure correctly!

# 1. Create a map config

To start, use the "Create a Map Configuration" from the home screen.

![CreateMapConfig](https://github.com/jetelain/ArmaRealMap/assets/33651126/166cd259-f0f5-4d46-ac66-a01c81786f11)

Alternatively you can go ```File > New > Arma 3 Map Config```


# 2. Select area with the map

Firstly you need to select an area in which to create a map, you navigate the map tool in the same way you use most map tools (Google Maps etc)
- Use the left mouse click (holding it down), to drag your view around the map.
- Use the mouse scroll wheel, to zoom in and out.

Once you have found your area and/or location where you wish to create a map, you will need to select the area:

Please note that an area you select will need to adhere to the following:
- Area MUST be square
- Area size IS NOT to exceeed 84x84km

## Option 1 : Select from center

You can select an area from it's center. Press the Alt key, then press the mouse left button on the center, then while pressing the mouse left button move the mouse to create a square around wanted area. When the square creates the wanted size, you can release the mouse button (it must remain within the map).

![FromCenter](https://github.com/jetelain/ArmaRealMap/assets/33651126/e43e4173-00fc-464b-90f1-ea571549aabd)

## Option 2 : Select from a corner

You can select an area from a corner. Press the Ctrl key, then press the mouse left button on on of the corcer, then while pressing the mouse left button move the mouse to the opposite corner to create a square around wanted area. When the square creates the wanted size, you can release the mouse button (it must remain within the map).

![FromCorner](https://github.com/jetelain/ArmaRealMap/assets/33651126/1957ba2b-5485-4fb1-b6f5-7cd566cf183b)


# 3. Edit Map Parameters
Using the "Advanced Parameters" section, you can edit important aspects of map creation. 

## Worldname

The Worldname is what this tool and other mods can/will use to refer to your world, this name MUST be unique and SHOULD contain a creators prefix.
- Having a Worldname that is not unqiue may/will create conflicts with other maps/worlds. 
- Adding a creators prefix ensures that the Worldname is even more likely to be unique, and also serves as an extra layer of Intellectual Property protection. 

Example: SMPX_Hawaii

## PBO Prefix

The PBO Prefix is what the exported pbo will be named. 
For the best workflow practices, you should copy the Worldname and paste it here, so that they are the exact same. 

## Tile Size

Leave this alone for now

## Resolution

Leave this alone for now

## Satellite Colour

Leave this alone for now

## Satellite Image Blend

The slider can be adjusted to blend between either the real/actual satellite image or the texture that Open Street Map has defined the area to be.

## Mod Directory

By default (without editing), this will show a ghost file path of where the created map will export itself to. 
Only add/change this if you need to modify where exported worlds/mods are sent. 


# 4. Asset Configuration

The area you have selected may not be suitable for the default assets that are included in the "CentralEurope.grma3a" asset pack. 

It is HIGHLY suggested that you browse through the [directory of premade asset packs](Asset-Pack-Directory) in order to find a pack that suits your maps' climate, rather than attempting to edit or even create your own asset pack. Ensure you download any of the required mods and that you install them into GRM Studio properly.

IF you have downloaded a premade asset pack, using the ```...``` you can navigate to where your downloaded .grma3a file is located (Usually in your downloads folder). 
IF you are not downloading a premade asset pack, and instead are using one of the 2 built-in asset packs, please, please, please, read the information located about them within the [directory of premade asset packs](Asset-Pack-Directory) as it contains important information about these 2 built-ins. 

## Installing mods into GRM Studio
In order to install mods, you will first need to ensure that you have actually subscribed and downloaded the mods you wish to use. 
Now within GRM Studio navigate the menu via ```Tools > Options > Arma 3 > Mods```, here you can tick (or untick) mods that you wish or to add (or unadd) to the studio application. 
Ensure you only add mods that will be 100% required to use the map 
- I.E. There is no need to add 3den Enhanced, as it is a soft dependency mod, and as such doesn't need to be added into GRM Studio in order to load/use a map. 


# 5. Generate Map for Arma 3
Selecting this buttom will bring up 2 options:

## Generate Map to a WRP file
ALWAYS select this, unless you are planning on using Arma 3's Terrain Builder tool... 

## Generate Map to Terrain Builder file
Only select this, if you no longer need to use GRM Studio's functions, and wish to export your OSM Map data into a file which can be used in Arma 3's Terrain Builder tool.

# 6. Generate Mod for Arma 3
Selecting this button will export your map configuration file and all it's layers into pbo and into a mod ready to be used in Arma 3. 
The amount of time for this process to do its thing and finish will vary on a variety of factors:
- The size of the area you have selected
- The complexity of the area you have selected
- The amount of assets that OSM has told GRM to add/place
- The hardware constraints of your own PC

You will know when the process has finished, as this will pop up:
![image](https://cdn.discordapp.com/attachments/1135252966144737290/1301280603664285786/image.png?ex=6723e780&is=67229600&hm=0658de7288dfe3e49d00ebe44293198c5ba4b8e74adb15b789e98846a12c6cc1&)

# 7. Using the Generate Mod
Adding it to the Launcher, Seeing in-game
1. Once the pop-up (As shown above) has appeared, select the "View in File Explorer" option. It should open up file explorer.
2. Go up 1 folder, so that now you are looking at a folder named @YourWorldName
3. Open up Arma 3 launcher, and drag the *above* folder onto the launcher.
    - It should now show at the bottom, ensure you press the "load mod" option. 
![image](https://i.gyazo.com/42d72486247071f31469ed8bc5817a4d.jpg)
4. Add any other additional mods that either you or your asset pack requires. 
5. Save the mods you have loaded as a preset.
6. Load the game
7. Open the map in 3den, via the Editor main screen, selecting your created map in the map options. 

# 8. Improve Your Map
You can now move onto improving your map!

You can use Eden Editor (Arma 3 builtin scenario editor) to edit map to improve the generator result. This is the recommended way for most users. See [Edit With Eden Editor](Edit-With-Eden-Editor).

You may otherwise use Terrain Builder to edit map, this tool is intended for experienced terrain makers. See [Terrain Builder Export](Terrain-Builder-Export).

Comparison of features of two edit process:

| Feature                   | [Eden Editor](Edit-With-Eden-Editor) | [Terrain Builder](Terrain-Builder-Export) |
|---------------------------|-------------------|----------------------------|
| Difficulty                | ★★               | ★★★★★★ (1)               |
| Speed                     | ★★★★            | ★★                        |
| Add objects               | Yes               | Yes                        |
| Remove objects            | Yes               | Yes                        |
| Replace objects           | Yes               | Yes                        |
| Edit objects              | Yes               | Yes                        |
| Edit terrain elevation    | With Deformer Mod | With Buldozer or external editor |
| Edit terrain textures     | No                | With Buldozer or external image editor |
| Edit satellite image      | No                | With external image editor |
| Edit roads                | No (2)            | Yes                        |
| Size limit                | No limit          | ~40x40 Km with 1 m/px resolution (3) |

(1) Terrain Builder is difficult to learn, but once mastered is extremely powerful.

(2) You may use roads objects, but they are not real roads.

(3) Terrain Builder can become really slow and may crash with large maps, it is a 32 bits process, whereas Arma 3 is 64 bits. You may be able to create larger maps, but it will cost you a lot of time.


# Resolving Issues

## Contribute to OpenStreetMap

You can fix issues in OpenStreetMap data by editing on OpenStreetMap.org, or simply improve data by adding more details.

WARNING: OpenStreetMap MUST remain the exact image of actual reality, **DO NOT ADD FICTIONAL DETAILS** to OpenStreetMap for your needs!

Follow the OpenStreetMap guidelines : https://wiki.openstreetmap.org/wiki/Contribute_map_data

## Contribute to GameRealisticMap

The generation process may have issue, or might do more job for you. Feel free to report issues or to create pull-request.

## Resolving General Issues

You can always ask questions on the Discord server (In the appropriate channel), if you encounter an issue not covered here. 

### ERROR: An error occurred trying to start process '...\Arma 3 Tools\...\....exe' with working directory 'C:\WINDOWS\system32'. The system cannot find the file specified.
Arma 3 tools has not been properly installed
- Ensure you have mounted the P Drive, and that it is currently showing as being mounted. 
- Ensure GRM Studio has the proper location of your Arma 3 Tools installation directory; ```GRM > Tools > Options > Arma 3 > General``` Tools location should be the same as it shows on steam ```Steam Library > Arma 3 Tools >RIGHT CLICK> Properties > Installed Files > Browse``` Compare the file explorer location of Arma 3 Tools with the GRM Studio, Tools location. 
- IF they match, reboot GRM Studio AND Arma 3 tools; check file path again, go back to export, see if Error occurs, if persists, try next steps OR ask on Discord. 
- IF they don't match, Uninstall Arma 3 tools, and then reinstall to the DEFAULT installation directory (Whatever your windows drive is (Usually C)). Refresh/Reopen GRM Studios, problem should be fixed, if not ask on Discord. 

### Unknown AnimType encountered: InsertStringNumbersHere
This is an issue with mod assets not being properly configured; unless a modder is able to fix this issue in their model.cfg, the asset that is causing the issue will be unable to be used in terrain generations.
