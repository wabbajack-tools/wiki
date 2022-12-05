# Native-Game-Installer - (Installers not using MO2)

The following guide explains how you set up a native or Mod Organizer 2 less Wabbajack compile of a folder structure for modding.

## Preparation of the modlist folder

Create a folder in which to create the list, and optionally create a `downloads` folder in side this modlist folder. Now add all the mods to this base folder and place the raw downloads from the nexus into the `downloads`.

## Create the compiler settings file

In the root of the modlist folder, create a file called "ListName.compiler_settings". Open it and set the contents to the following:

```json
{
  "Source": "E:\\wj_tmp\\dishonored",
  "Downloads": "E:\\wj_tmp\\dishonored\\downloads",
  "Game": "Dishonored",
  "OutputFile": "E:\\wj_tmp"
}

```

## Build your setup

Now you can go ahead and build your setup how you need and want it.

## Opening Wabbajack to Compile the List

From here on out just move on to the next Chapter.
