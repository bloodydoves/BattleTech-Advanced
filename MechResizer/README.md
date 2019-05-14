# Mech Resizer

BattleTech Mod (using [BTML](https://github.com/Mpstark/BattleTechModLoader) and [ModTek](https://github.com/Mpstark/ModTek)).

Change the size of mechs, vehicles, and turrets. Always wanted a 200 meter tall Locust? Now you can!

This is primarily intended as a tool for other modders. There is a configuration file (likely out of date) [here](/mod.json.sample) with lore appropriate sizes for some mechs.

## Features
* change the default size of all mechs
* change the size of mechs based on prefab
* change the size of any specific mech based on chassis or tags
* change the default size of all vehicles
* change the size of any specific vehicle based on chassis or tags
* change the default size of all vehicles
* change the size of any specific vehicle based on chassis or tags
* change the default size of some (missiles only for now) projectiles
* change the size of some (missiles onlye for now) specific projectiles


## Download
Downloads can be found on [Github](https://github.com/janxious/MechResizer/releases).

## Install
- [Install BTML and Modtek](https://github.com/Mpstark/ModTek/wiki/The-Drop-Dead-Simple-Guide-to-Installing-BTML-&-ModTek-&-ModTek-mods).
- Put the `MechResizer.dll` and `mod.json` files into `\BATTLETECH\Mods\MechResizer` folder.
- If you want to change the settings do so in the `mod.json` or by adding appropriate tags to chassis files.
- Start the game.

## Settings

All resize settings are exclusive, so you cannot apply layered resizing i.e. a default of 1.1 will not multiply a tag of 2. Resizing preference is in the following order: vector supplied in `<TYPE>ResizeMultiplierVectors`, tags, `<TYPE>ResizeMultipliers`, prefab, `mod.json`-supplied default, and a hard-coded default of 1.25.

The dimensions for the `*Vectors` settings are measured like: <X> - width (shoulder to shoulder), <Y> - height (toes to head), <Z> - depth (chest to back)

### Tag-Based Resizing
In addition to the settings that follow that are set in `mod.json`, you can also change the size of elements using tags. There are two formats:

1. `mr-resize-N`: `N` can be an integer or decimal number and will resize the given item equally in all dimensions
2. `mr-resize-X-Y-Z`: `X`, `Y`, and `Z` can be an integers or decimal numbers and will scale on that axis

The tags must be put in the following type of file to be applied:

Type | File Type | Tag Location
--- | --- | ---  
Mechs | `data/chassis/chassisdef_<variant>.json` | `ChassisTags`->`items`
Vehicles | `data/vehicle/vehicledef_<variant>.json` | `VehicleTags`->`items`
Turrets | `data/turrets/turretdef_<variant>.json` | `TurretTags`->`items`
Projectiles | `data/weapon/Weapon_<variant>.json` | `ComponentTags`->`items`

### `mod.json` settings
Setting | Type | Default | Description
--- | --- | --- | ---
`debug` | `boolean` | false | enable debug logging
`defaultMechSizeMultiplier` | float | 0.9 | override this to globally change all mech sizes in combat. Vanilla is 1.25
`defaultVehicleSizeMultiplier` | float | 1 | override this to globally change all vehicle sizes in combat. Vanilla is 1
`defaultTurretSizeMultiplier` | float | 1 | override this to globally change all turret sizes in combat. Vanilla is 1
`defaultProjectileSizeMultiplier` | float | 1 | override this to globally change certain weapon (missiles only ATM) projectile sizes in combat. Vanilla is 1
`mechSizePrefabMultipliers` | json hash | {} | change the size of any set of mechs that share a common `PrefabBase` in their chassis definition files. For example, making all highlander variants very large might look like: `"highlander": {"x": 8, "y": 8, "z": 8}`
`vehicleSizePrefabMultipliers` | json hash | {} | change the size of any set of vehicles that share a common `PrefabBase` in their vehicle chassis definition files.
`turretSizePrefabMultipliers` | json hash | {} | change the size of any set of turrets that share a common `PrefabBase` in their turret chassis definition files.
`projectileSizePrefabMultipliers` | json hash | {} | change the size of any set of projectiles that share a common `PrefabBase` in their weapon firing them's weapon definition files.


### Deprecated `mod.json` Settings - please use the size change options above î
Setting | Type | Default | Description
--- | --- | --- | ---
`mechResizeMultipliers` _deprecated_ | json hash | {} | change the size of mechs using the format `"chassis string" : multiplier`. A big locust would be like `"chassisdef_locust_LCT-1V": 15`
`mechResizeMultiplierVectors` _deprecated_ | json hash | {} | change mech sizes using three dimensional multipliers with format `"chassis string": { "x": Xmulti, "y": Ymulti, "z": Zmulti }`. A very tall locust might look like `"chassisdef_locust_LCT-1V": {"x": 1,"y": 2, "z": 1}``
`vehicleResizeMultipliers` _deprecated_ | json hash | {} | change the size of vehicles using the format `"chassis string" : multiplier`. A big APC would be like `"vehiclechassisdef_APC_Wheeled": 3`
`vehicleResizeMultiplierVectors` _deprecated_ | json hash | {} | change vehicle sizes using three dimensional multipliers with format `"chassis string": { "x": Xmulti, "y": Ymulti, "z": Zmulti }`. A very long APC might look like `"vehiclechassisdef_APC_Wheeled": {"x": 1,"y": 1, "z": 2}``
`turretResizeMultipliers` _deprecated_ | json hash | {} | change the size of turrets using the format `"chassis string" : multiplier`. 
`turretResizeMultiplierVectors` _deprecated_ | json hash | {} | change turret sizes using three dimensional multipliers with format `"chassis string": { "x": Xmulti, "y": Ymulti, "z": Zmulti }`.
`projectileResizeMultipliers` _deprecated_ | json hash | {} | change the size of projectiles using the format `"weapon id string" : multiplier`.
`projectileResizeMultiplierVectors` _deprecated_ | json hash | {} | change projectile sizes using three dimensional multipliers with format `"weapon id string": { "x": Xmulti, "y": Ymulti, "z": Zmulti }`.

## Screenshots

Big Locust

<img width="885" alt="screen shot 2018-05-22 at 2 08 16 pm" src="https://user-images.githubusercontent.com/50124/40382747-306be6b8-5dcd-11e8-8956-078891fd6722.png">

Big Everythings

<img width="973" alt="screen shot 2018-05-22 at 2 26 07 pm" src="https://user-images.githubusercontent.com/50124/40382748-30800814-5dcd-11e8-8de0-f1943be2af53.png">


## Sample Fun Config

Normal vehicles size, smaller than vanilla mechs, slenderman griffin, giganto thunderbolt, weirdly stretched galleon, giganto striker, and some big missiles.

```
{
  "Name": "MechResizer",
  "Enabled": true,

  "Version": "1.0.0",

  "Author": "janxious",
  "Website": "https://github.com/janxious/MechResizer",

  "DLL": "MechResizer.dll",
  "DLLEntryPoint": "MechResizer.MechResizer.Init",
  "DependsOn": [],
  "ConflictsWith": [],

  "Settings": {
    "defaultMechSizeMultiplier": 0.9,
    "mechSizeMultipliers": {
      "chassisdef_thunderbolt_TDR-5SE": 4
    },
    "mechSizeMultiplierVectors": {
      "chassisdef_griffin_GRF-1N": { "x": 1, "y": 2, "z": 1 }
    },

    "defaultVehicleSizeMultiplier": 1,
    "vehicleSizeMultipliers": {
      "vehiclechassisdef_STRIKER": 4
    },
    "vehicleSizeMultiplierVectors": {
      "vehiclechassisdef_GALLEON": { "x": 2, "y": 4, "z": 2 }
    },
    
    "defaultTurretSizeMultiplier": 1,
    "turretSizeMultipliers": {},
    "turretSizeMultiplierVectors": {},
        
    "defaultProjectileSizeMultiplier": 1,
    "projectileSizeMultipliers": {
       "Weapon_SRM_SRM2_0-STOCK": 1.5
    },
    "projectileSizeMultiplierVectors": {
       "Weapon_SRM_SRM4_0-STOCK": { "x": 1.5, "y": 1.5, "z": 1.5 }
    }
  }
}
```

## Special Thanks

HBS, @Mpstark, @Morphyum


## Maintainer Notes: New HBS Patch Instructions

* pop open VS
* grab the latest version of the assembly
* copy the new version of the methods in `original_src` over the existing ones
* see if anything important changed via git
