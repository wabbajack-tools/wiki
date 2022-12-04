# Compilation Settings

Compilation itself is very straight forward and similar to Installation: you let Wabbajack run and hope it finishes successfully. The key for making it run successfully is having a "Wabbajack-compliant" MO2 setup which you can get by following the advice from the previous chapters.

## Find or Generate your .compiler_settings

- Click on the three dots next to the `Compiler Settings` field.
- In the file chooser that opens you have to:
  - If it is your first time compiling a list, navigate to `profiles/{profile_name}/` and select the `modlist.txt` this will generate the required `.compiler_settings` file for this and future compiles
  - If you already have used Wabbajack with the Mod Organizer 2 instance you want to compile before or are using [07. Native-Game-Installer - (Installers not using MO2)](Native-Game-Installer%20-%20(Installers%20not%20using%20MO2).md) then you switch the filetype form `MO2 Modlist (.txt)` to `Compiler Settings File (.compiler_settings)` and select the `ModlistName.compiler_settings` file

## Download Location

The download location is the path to the folder where all your archives and `.meta` files are located.

## Output Location

The location where the modlist `.wabbajack` file will be outputted too.

## Wabbajack Compilation Configuration Editor

In Wabbajack select _Create a Modlist_ to navigate to the configuration screen. Here you can configure some metadata for your Modlist which will later be viewable by the user.

| Field               | Description                                                                                                                 | Notes                                                                                                                                                                               |
|---------------------|-----------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Modlist Name        | **REQUIRED:** Name of your Modlist                                                                                          |                                                                                                                                                                                     |
| Version             | **REQUIRED:** Current Version                                                                                               | Do note that this has to be a semantic version (1.0 or 0.1 (it can have multiple`.` separators)) and not some random text like "The best version on Earth" (this is not the Nexus)! |
| Author              | Modlist Author                                                                                                              | Should be your name in original Modlists and/or the name of the original Modlist author if you adapted a normal Modlist to a Wabbajack Modlist                                      |
| Description         | 700 characters Descriptions                                                                                                 |                                                                                                                                                                                     |
| Image               | Modlist Image                                                                                                               | Aspect ratio should be 16:9 for the best result                                                                                                                                     |
| Website             | Website URL                                                                                                                 |                                                                                                                                                                                     |
| Readme              | **REQUIRED:** Readme URL                                                                                                    | Link to the readme mentioned in                                                                                                                                                     |
| NSFW                | NSFW Checkbox                                                                                                               | Only really needed for official Modlists as our Galleries have the option to hide NSFW Modlists                                                                                     |
| Publish Update      | Publish Update Checkbox                                                                                                     | If you completed [Getting CDN Access](../wabbajack_cdn_and_gallery_access/Getting%20CDN%20Access.md) and [Adding a Custom Repository to Wabbajack](../wabbajack_cdn_and_gallery_access/Adding%20a%20Custom%20Repository%20to%20Wabbajack.md) you can use this option to automatically publish your list                                  |
| MachineUrl          | machineURL of the modlist required for `Publish Update`                                                                     | [Adding a Custom Repository to Wabbajack](../wabbajack_cdn_and_gallery_access/Adding%20a%20Custom%20Repository%20to%20Wabbajack.md) Is referencing this field with its `JohnsLists/JohnsSkyrimMakeover` Example                                                             |
| Nomatch Include     | Adds folders to a list from which all content that can't be matched to a source should be included still                    | Useful for custom patches or generated files                                                                                                                                        |
| Include             | Adds files and folders to a list which will be included with the .wabbajack file                                            | **DO NOT USE ON DOWNLOADED MODS** As it would result in you distributing that mod. Can lead to large `.wabbajack` files if used unsparingly                                         |
| Ignore              | Adds files and folders to a list that will be ignored and therefore will not be part of final installations                 | Useful for mods and tools you use during development you don't want included in the final installation                                                                              |
| Other Profiles      | Adds profile folders to a list for other MO2 profiles you want to include in the final installation                         | Useful for performance, or content profiles                                                                                                                                         |
| Always Enabled Mods | Adds mod folders to a list of mods that will be included in your list no matter if they are enabled (active in game) or not | Wabbajack will normally ignore all mods you disabled in MO2 but there are some cases where you might want to give some choice to the end user and want to have the mod included     |

## Compilation Errors

You will likely get a ton of errors during your first compilation which is to be expected. We highly recommend you join our [Discord](https://discord.gg/wabbajack) and check the `modlist-development-help` channel for help.
