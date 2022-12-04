# Keeping the Game Folder clean

## Overview

The general idea is that we need a way to keep the Vanilla games clean in their installation locations, so that we don't cause issues with other tools or modlists, but there are files and mods that need to be in the games directory. For this there are two solutions both with their own pros and cons, Root Builder and A "Stock Game" copy inside MO2 Instances.

## Root Builder

Since the author of the Tool can describe it best here an excerpt from their website:

> Root Builder is a plugin for Mod Organizer 2, allowing users to manage files in the base game directory through Mod Organizer.
>
>Some of the things you can do with Root Builder:
>
>- Install script extenders (SKSE, OBSE, FOSE, etc) through Mod Organizer.
>- Install ENB and different presets for it through Mod Organizer.
>- Manage different versions of the same game as mods within Mod Organizer.
>- Keep your game folder untouched and as clean as the day it was installed.
>- Keep all your mods in Mod Organizer, saving your setup if you need to reinstall or switch computer.

Source: [Root Builder Website](https://kezyma.github.io/?p=rootbuilder)

| Pros                                                                                                                      | Cons                                                                                                                   |
| ------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| Can use different root folder Binaries depending on different supported platforms like Steam or GOG by using MO2 Profiles | You need to be careful with game updates, if the game updates the binaries for that version might not be there anymore |
| Can use different ENB presets in different performance MO2 Profiles                                                                                                                          |                                                                                                                        |
| Requires less storage space                                                                                               |                                                                                                                        |

For using Root Builder we recommend the very on point and well written official instructions on the [official website](https://kezyma.github.io/?p=rootbuilder#intall-col).
A guide that also features compiling with Root Builder can be found [here](https://github.com/The-Animonculory/Modding-Resources/blob/main/Root%20Builder%20for%20Skyrim%20AE.md).

## Stock Game

The general idea is to build a WJ modlist that stores the game files inside the MO2 install folder.
WJ will recognize these files and copy them from the end-user's game folder. This has the side-effect of keeping the game folder completely clean.

| Pros                        | Cons                                                                                                |
| --------------------------- | --------------------------------------------------------------------------------------------------- |
| Game updates can't break it | requires a lot of storage space                                                                     |
|                             | locked into one specific platform (only users owing the game on the same store can use the modlist) |
|                             | Can only include one ENB preset                                                                                                    |

### Preperation

1) Build a WJ list as normal
2) Create a folder in the MO2 base folder, let's call it `Stock Game`, so users don't think these are `Game Folder Files`
3) Copy in all the game files from your `Skyrim Special Edition` folder
4) Remap MO2 files, open `Mod Organizer.ini` and change `GamePath=` to `c:\\Path\\To\\MO2\\Stock Game`
5) Open MO2 and edit the custom executable paths for SKSE/Launcher/Skyrim to the new path inside the MO2 folder

### Optimization

Doing the above will add about 12GB of bloat to the installed modlist, but we can likely reduce this quite a bit.

- Any `.ESMs` that have been cleaned are no longer required (as the cleaned files are in a mod), so delete those .ESMs from `Stock Game\\Data`
- Any `.BSA` that are 100% replaced with files by the same name can be removed. So if you're using `unofficial performance optimized textures`, you can safely delete all the Texture BSAs

### Final setup

You can now put any ENBs, .dlls, etc. Directly into the `Stock Game` folder.

Users should now be able to Install via WJ -> MO2 -> Run SKSE, removing the rather "complicated" step of copying game files into the game folder. This also allows multiple lists to be installed at one time that use the same base game, removing the need for a ENB manager.
