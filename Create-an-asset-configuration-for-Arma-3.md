# Introduction to asset configuration


## 1. Create an empty asset configuration

To create an asset configuration, you can use the "Create an Asset Configuration" from the Home screen. The actions is also available in File menu, New, Arma 3 Assets Configuration.

![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/58e8423f-13a3-4e1b-9e41-c0d8d3e83d46)

Create a fully functional asset configuration is hard (due to the Arma Configuration part). **We strongly recommend you to use the Quick Start**, and start from a builtin configuration that you will edit to fit your needs.

![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/5fd9485f-efdb-4af4-976a-ded55064e66a)

## 2. Explorer

The explorer is a tool that allows you to see all the config pages of the opened files, and have a quick access to them.

To open explorer, go in View menu, then click on Explorer.

![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/df25b20d-ea9a-4993-8c94-7a551ed2afbd)

![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/9be1012b-3099-4aed-82f1-9e79683f08df)

## 3. Asset Browser

Open Asset Browser with button in Home screen, or from the Tool menu.

![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/3fc7c8a5-ab02-40a4-beda-95381af38e93) or ![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/253bfc98-cc06-40f0-8a68-892f4e9566ee)

The asset browser let you see all available objects that you can use within an asset configuration.

To get started, you need to import objects. By default base game assets will be automatically imported on first start. To import objects use the Import objects buttons, then select the appropriate set.

![image](https://github.com/jetelain/ArmaRealMap/assets/33651126/3ca88f5f-6ecb-4dc6-8784-7a88e95f15c9)

Common mods have shortcut. To add their content you will have to subscribe to them on Steam if it's not yet done (Steam will open if you ask a mod that have not been subscribed).

Objects are automatically typed, you can change type using the contextual menu on item with a right click. You can also remove objects that have no interest for your maps.

One you have found an object suitable for your need, you can drag-and-drop it to the explorer.

![drag-and-drop to the explorer](https://github.com/jetelain/ArmaRealMap/assets/33651126/c899ea54-e7ac-4cea-af73-b94067865aeb)

or to the config page (using a side-by-side view)

![N8ztHcqrku](https://github.com/jetelain/ArmaRealMap/assets/33651126/13d96d28-5332-489e-9ca8-c349d570f5c8)

To use object from other mods, open application settings, in mods sections, check mods you need than click on Ok. Then go back to asset browser, click on Import assets, you will find if in Active mods.

# Natural areas

Natural areas are filled with objects specified in the asset configuration. For each areas multiple objects types are used for filling using two algorithms. Most area are filled by two sets of objects (main then additional).

Each natural area have also a specific ground texture, which includes random small ground objets (clutter). See dedicated section for details.

You can add multiple variations for each type. For each area a variation will be randomly chosen.

## Density

On each pane you can define density. Density is randomly chosen between two values for each area. If the two values are equal, the value is always the same.

It's important to test configuration, to ensure that density is not too high. The preview module, at the end of each module is intend for that. The Generate Preview button will tell you if density is correct. It will apply the algorithm on a 200x200m area.

Note: If density is too high, the generation process will be extremely slow, as system will try very hard to generate as many as possible objets positions but will likely fail to do so.

## Object properties

Each object used to fill an area has some properties :
- Probability: probability of object to be chosen (within collection, or seed depending on algorithm)
- Radius: it's used to compute distance between objects within area. Each object is associated to a circle with that radius, and no other object circle must overlap it.
- Fit radius: it's used to ensure that object will fit in the area, to avoid overflow.
- Max Z, Min Z: elevation offset to apply on object, value is random between the two limits (optional, Min Z must be lower than Max Z)
- Max Scale, Min Scale: scale to apply on object, value is random between the two limits (optional, Min Scale must be lower than Max Scale) 

Object heading is always random.

Recommandations :
- reduce computed radius to a smaller value to allow objects overlap in a natural manner.
- set fit radius to zero for narrow areas such as forest edge
- set larger fit radius for large non square / non round objects (such as large rock objects)

| Radius smaller than Fit radius |  Radius larger than Fit radius |
|--------------------------------|--------------------------------|
| ![RadiusSmallerThanFit](https://github.com/jetelain/ArmaRealMap/assets/33651126/aa68d02e-101c-4526-87d5-2a6a51a30337) | ![RadiusLargerThanFit](https://github.com/jetelain/ArmaRealMap/assets/33651126/5905afb4-7bab-4ed9-8449-84c12a182ed9) |
| Keep objects away from boundary, but still allows objects to overlap | Allows object to overlap and overflow |

## Filling algorithms

### Pure random

This algorithm is great for artificial or mineral objects, or low density vegetation.

It picks a random position within area, then picks a random object from the configuration, if the object fits within area and does not collide with existing objects, it's kept.

This is done until enough objects have been placed.

### Seed based

This algorithm is great for vegetation, it aims to mimic vegetation placement: next to a plant, you will have an high probability to find a plant of the same species.  

First it generates "seeds" within the area at random positions.

It picks a random position within area, then looks for "seeds" close to the position, and take a random one. Then it picks a random object from the seed configuration, if the object fits within area and does not collide with existing objects, it's kept.

This is done until enough objects have been placed.

## Forest

| Area              | Algorithm   | Purpose                                 |
|-------------------|-------------|-----------------------------------------|
| Forest            | Seed based  | Main trees                              |
| Forest Additional | Pure random | Dead trees, rocks, bushes, etc.         |
| Forest Edge       | Seed based  | Bushes at edges of forest               |
| Forest Radial     | Seed based  | Trees near forest to avoid sharp limits |

Forest trees should have a smaller radius than object shape to allow overlap of trees, and to keep room for additional objects.

Forest Edge objects should have a Fit Radius of 0, or a really small value, to reduce constraints on object position.

## Scrubs

| Area              | Algorithm   | Purpose                                     |
|-------------------|-------------|---------------------------------------------|
| Scrubs            | Seed based  | Bushes                                      |
| Scrubs Additional | Pure random | Rocks, dead bushes                          |
| Scrubs Radial     | Seed based  | Bushes near main area to avoid sharp limits |

## Rock areas

| Area              | Algorithm   | Purpose                                     |
|-------------------|-------------|---------------------------------------------|
| Rocks             | Pure random | Large rock blocks                           |
| Rocks Additional  | Pure random | Medium and small rocks, bushes to fill gaps |

## Watercourse

| Area                   | Algorithm   | Purpose                                     |
|------------------------|-------------|---------------------------------------------|
| Watercourse            | Seed based  | Water plants within river                   |
| Watercourse Additional | Pure random | Erosion rocks within river                  |
| Watercourse Radial     | Seed based  | Bushes and small trees close to rivers      |

# Fences, Walls


# Buildings


# Objects


# Ground textures
You need to either use the pre-existing textures or create your own --INSERT LINK to creating ground detail textures--


# Roads