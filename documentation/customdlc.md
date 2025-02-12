![Documentation Image](images/documentation_header.png)

## [CUSTOMDLC] Header
The [CUSTOMDLC] header is likely the most important header for mod developers. It allows Mod Manager to add a Custom DLC folder to the game, such as DLC_MOD_EGM. This header has some advanced optional descriptors that allow you to add compatibility shims and packs automatically when the mod loads in Mod Manager. This header is supported starting with moddesc 3.1.

The following descriptors are supported by this header. The alternates are explained on the alternates page.

### [CUSTOMDLC] Descriptors
|Descriptor|Value|Purpose & Notes|Required|Supported Versions|
|--- |--- |--- |--- |--- |
|sourcedirs|Unquoted Semicolon Separated List (String)|List of directory names in this mod folder that will be installed into the game's DLC folder.|Yes|3.1+|
|destdirs|Unquoted Semicolon Separated List (String)|List of directory names that will be created in the game's DLC folder. The corresponding folder in the sourcedirs list will be placed here. Typically the destdirs and sourcedirs list are identical, but they can be different if you prefer a different naming scheme.|Yes|3.1+|
|altfiles|Unquoted Comma Separated List (AltFile)|List of AltFile structs that define an alternative set of files to install (or not install). You can make these alternate files automatically part of the mod (such as substituting a file if a DLC exists) or have them be manually chosen by the user, like game files that use lower resolution. See the AltFile struct information below.|No|4.2+|
|altdlc|Unquoted Comma Separated List (AltDLC)|List of AltDLC structs that define an alternative set of Custom DLC to install (or not install). You can make these alternate dlcs automatically part of the mod (such as adding a DLC if another DLC is not present) or have them be manually chosen by the user, like adding more squadmates to a mod. You can also add files to an existing Custom DLC that you are going to install if you want to have a modular style CustomDLC that is customized for every user. See the AltDLC struct information below.|No|4.4+|
|outdatedcustomdlc|Unquoted Semicolon Separated List (String)|List of foldernames that should not be present in the game's DLC folder after installation. You can use this descriptor to have Mod Manager delete old versions of the mod (if you renamed it), remove outdated compatibility packs, and remove known incompatible mods. The user is prompted to delete the folders if any exist.|No|4.4+|
|incompatiblecustomdlc|Unquoted Semicolon Separated List (String)|List of DLC foldernames that are known to be fully incompatible with your mod - e.g. installing both mods would break the game for the user. If any item in this DLC list is found, the mod will refuse to install. Putting the name of any official DLC will cause your mod to fail validation.|No|6.0+|
