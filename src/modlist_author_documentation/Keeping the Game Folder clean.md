# Keeping the Game Folder clean

## Overview

In order to allow installing multiple modlists on the same system for the same game, we need a way to keep the vanilla games clean and unmodified in their respective installation locations to ensure no conflicts with other tools or modlists. However, for every modlist, there are files and mods that **must** reside in the game directory. There are two ways to tackle this: RootBuilder, or a "Stock Game" copy inside an MO2 instance.

## RootBuilder

Since the author of the tool can describe it best, here an excerpt from their website:

> RootBuilder is a plugin for Mod Organizer 2, allowing users to manage files in the base game directory through Mod Organizer.
>
> Some of the things you can do with RootBuilder:
>
> -   Install script extenders (SKSE, OBSE, FOSE, etc) through Mod Organizer.
> -   Install ENB and different presets for it through Mod Organizer.
> -   Manage different versions of the same game as mods within Mod Organizer.
> -   Keep your game folder untouched and as clean as the day it was installed.
> -   Keep all your mods in Mod Organizer, saving your setup if you need to reinstall or switch computer.

Source: [RootBuilder Website](https://kezyma.github.io/?p=rootbuilder)

| Pros                                                                                                                      | Cons                                                                                                               |
| ------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| Can use different root folder binaries depending on different supported platforms like Steam or GOG by using MO2 Profiles | You need to be careful with game updates--if the game updates, the binaries for that version may not exist anymore |
| Can use different ENB presets in different MO2 profiles                                                                   |                                                                                                                    |
| Requires less storage space                                                                                               |                                                                                                                    |

For using RootBuilder, we recommend following the [official instructions](https://kezyma.github.io/?p=rootbuilder#intall-col).
A guide that also features compiling with RootBuilder can be found [here](https://github.com/The-Animonculory/Modding-Resources/blob/main/Root%20Builder%20for%20Skyrim%20AE.md).

## Stock Game

The Stock Game method involves building a WJ modlist that stores the game files _inside_ the MO2 install folder.
WJ will recognize these files and copy them from the end-user's game folder. This has the side-effect of keeping the game folder completely clean.

| Pros                        | Cons                                                                |
| --------------------------- | ------------------------------------------------------------------- |
| Game updates can't break it | Requires a lot of storage space                                     |
|                             | Locked to one platform (e.g., Steam _only_ or GOG _only_--not both) |
|                             | Can only include one ENB preset                                     |

### Preperation

1. Build a WJ list as normal
2. Create a folder in the MO2 base folder, let's call it `Stock Game`, so users don't think these are `Game Folder Files`
3. Copy in all the game files from your `Skyrim Special Edition` folder
4. Remap MO2 files, open `Mod Organizer.ini` and change `GamePath=` to `c:\\Path\\To\\MO2\\Stock Game`
5. Open MO2 and edit the custom executable paths for SKSE/Launcher/Skyrim to the new path inside the MO2 folder

### Optimization

Doing the above will add about 12 GB of bloat to the installed modlist, but we can likely reduce this quite a bit:

-   Any `.ESM`s that have been cleaned are no longer required (as the cleaned files are in a mod), so delete such `.ESM`s from `Stock Game\\Data`
-   Any `.BSA` that are 100% replaced with files by the same name can be removed. So if you're using `unofficial performance optimized textures`, for instance, you can safely delete all the texture BSAs

### Final Setup

You can now put any ENBs, `.dll`s, etc. directly into the `Stock Game` folder.

Users should now be able to Install via WJ -> MO2 -> Run SKSE, circumventing the rather complicated step of copying game files into the game folder. This also allows multiple lists to be installed at the same time that use the same base game, removing the need for an ENB manager.
