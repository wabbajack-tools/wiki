# Native-Game-Installer (Installers not using MO2)

The following guide explains how to set up a "native" (or MO2-less) Wabbajack compilation for any given folder structure.

> **Warning**
> This Page potenitally requires updating the template for Wabbajack version 3.0.

## Preparing the Modlist Folder

Create a folder in which to create the list, and optionally create a `downloads` folder in side this modlist folder. Now add all the mods to this base folder and place the raw downloads from the nexus into the `downloads`.

## Creating the `.compiler_settings` File

In the root of the modlist folder, create a file called "ListName.compiler_settings". Open it and set the contents to the following:

```json
{
    "Source": "E:\\wj_tmp\\dishonored",
    "Downloads": "E:\\wj_tmp\\dishonored\\downloads",
    "Game": "Dishonored",
    "OutputFile": "E:\\wj_tmp"
}
```

## Building Your Setup

Now you can go ahead and build your setup as needed.

## Opening Wabbajack to Compile the List

See the next chapter for further instructions.
