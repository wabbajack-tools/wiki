# Pre-Compilation

Compilation is similar to Installation in that one configures some filesystem paths, starts the process, and waits for Wabbajack to finish. Wabbajack requires a rather specific MO2 setup and you might have to change your workflow when developing a modlist.

## Everything Comes from Somewhere

> Wabbajack is an automated modlist installer that can reproduce an entire modding setup on another machine without bundling any assets or re-distributing any mods.

The focus is on "_without bundling any assets or re-distributing any mods_." This means that Wabbajack needs to know where **every single file** originates. The most common origin is your downloads folder.

If you take a quick look inside your MO2 downloads folder you will find 2 types of files:

1. The actual download (some archive, e.g. `.7z`, `.zip`, `.rar`)
2. A `.meta` file that has the same name the archive it is associated with

For instance, you might have `SkyUI_5_1-3863-5-1.7z` and `SkyUI_5_1-3863-5-1.7z.meta`.

These `.meta` files are created by MO2 and typically get created when you click the **`MOD MANAGER DOWNLOAD`** button on Nexus Mods. If you open the `.meta` file you will find some metadata for the associated archive, the most important entries being `fileID`, `modID` and `gameName`.

Wabbajack will use these `.meta` files to determine where each archive originates using the [Nexus Mods API](https://app.swaggerhub.com/apis-docs/NexusMods/nexus-mods_public_api_params_in_form_data/1.0#/). This means that you **should** use the **`MOD MANAGER DOWNLOAD`** button on Nexus Mods or you will have to create `.meta` files manually. Note: you may also use the **`Query Info`** context menu option after dropping an archive into the MO2 `Downloads` tab. Doing so will retrieve the metadata of the selected archive and create an associated `.meta` file.

For more information on `.meta` files, support sites, and instructions for how to create them, see the [Meta Files](Meta%20Files.md) section.

## Mod Organizer 2

You now know about `.meta` files and understand that every file _has to come from somewhere_. This implies that you must create `.meta` files for MO2 and files in your game folder. You need to be using the zipped version of the [MO2 GitHub Releases](https://github.com/ModOrganizer2/modorganizer/releases/) instead of the ones you can find on the Nexus and instead of the installer to avoid issues.

## Utility Outputs

Outputs from utility's from VRAMR or ParallaxGen are **strictly** forbidden from being uploaded on both Nexus and the Wabbajack CDN. If you want to include such outputs, you must include the original mods downloads in your download folder with appropriate meta files. Wabbajack will then create patches during the compilation process to turn the original mod files into the outputs. 

## Patches

Having read the preceding sections, you may be wondering if Wabbajack is able to detect modified files and, if so, how it deals with them. Wabbajack cannot inline modified files, so instead we just include the difference between the original and modified version.

This basically means `original + patch = final` and we only include `patch` in the `.wabbajack` file which, by itself, is just gibberish and completely useless without the original file. This allows us to distribute arbitrary changes without violating copyrights as we do not distribute any copyrighted material. Instead, we copy instructions on how to modify the copyrighted material.

In fact, you don't even have to tell Wabbajack that a specific file was modified--that would be way too much work! Instead, Wabbajack will figure out which files have been modified automagically and create [binary patches](https://vickieli.dev/binary%20exploitation/intro-to-binary-patching/). The modified files can be anything--configuration files, plugins, textures, etc.--and Wabbajack will automatically generate and inline the necessary binary patches for each.

## BSA Decomposition

Wabbajack is able to both **analyze and create** `.bsa` and `.ba2` files. Accordingly, any changes made to a BSA/BA2 are replicated in the end-user's installation. This process may include the creation of new BSAs or patching existing ones. Unpacking, modifying, and repacking a BSA is fully automated, and modifications will appropriately carry over to each end-user install. BSAs packed manually by a modlist author are also replicated in a similar fashion. Wabbajack does not analyze a BSA as a whole--instead, it unpacks the BSA, hashes the files within, and compares them to their original sources. It then packs the BSA (if new) or repacks it (if modified) as necessary. Note that with particularly large BSAs this building and rebuilding process can take a significant amount of time on the end-user's machine depending on their hardware specifications.

## Merges

Similar to BSAs, Wabbajack is able to analyze and create merged mods. Wabbajack will source the necessary files to create the merge from the previously mentioned sources and rebuild the merge on the user-end. Generally, it is recommended to mark merges as `No Match Include` (see [Compilation - Settings](Compilation%20Settings.md)) to ensure that any files generated by the merging process are also carried over to the user. Wabbajack does not, by default, include the files and information necessary to build or rebuild the merge in the program used to build the merge originally--only the merge itself will be installed.

## Minimal Downloads Folder

Wabbajack will _match_ files to determine where they came from. Rarely, this may not work as intended and Wabbajack may end up matching files against the wrong archives. This can happen when you have multiple versions of the same mod in your downloads folder. Additionally, Wabbajack will download every archive that exists in _your_ downloads folder into the end-user's downloads folder. Therefore, it is highly recommended that you **delete unused downloads and previous versions of mods from your downloads folder frequently** so that Wabbajack doesn't end up mis-matching files and the end user doesn't end up downloading more archives than they need.

## Configurations Superseded by Compiler Settings within the Wabbajack App

**IMPORTANT: The following method has been superseded. It may still be used to guarantee backwards compatibility for compiling lists made for Wabbajack 2.5 with Wabbajack 3.0. The new method to manage these options is described in [Compilation - Settings](Compilation%20Settings.md).**

### Special Flags (Superseded)

In some cases, we would like to modify Wabbajack's default behavior for a specific mod. To do so, you may place the following flags in the notes or comments section of a mod to change how Wabbajack handles that mod:

| Flag                        | Description                                                    | Notes                                                                                                                                                                           |
| --------------------------- | -------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `WABBAJACK_INCLUDE`         | All mod files will be inlined into the`.wabbajack` file        | **DO NOT USE ON DOWNLOADED MODS** As it would result in you distributing that mod. Can lead to large `.wabbajack` files if used unsparingly                                     |
| `WABBAJACK_NOMATCH_INCLUDE` | Any unmatched files will be inlined into the`.wabbajack` file  | Useful for custom patches or generated files                                                                                                                                    |
| `WABBAJACK_ALWAYS_ENABLE`   | The mod will not be ignored by Wabbajack even if it's disabled | Wabbajack will normally ignore all mods you disabled in MO2 but there are some cases where you might want to give some choice to the end user and want to have the mod included |
| `WABBAJACK_ALWAYS_DISABLE`  | The mod will always be ignored by Wabbajack                    | Useful if you don't want some mods included in the Modlist but still want to keep it active in your own setup                                                                   |

### Tagfile Tags (Superseded)

You can create an empty `tagfile` with no extention in any folder you want to apply this tags to. This is meant to be used with folders that aren't mods.

| Flag/File                             | Description                                                                                                    | Notes                                                                                                                                                                    |
| ------------------------------------- | -------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `WABBAJACK_INCLUDE`                   | All files in this folder will be inlined into the`.wabbajack` file                                             | **DO NOT USE ON DOWNLOADED MODS** As it would result in you distributing that mod. Can lead to large `.wabbajack` files if used unsparingly                              |
| `WABBAJACK_NOMATCH_INCLUDE`           | Any unmatched files will be inlined into the`.wabbajack` file                                                  | Useful for custom patches or generated files                                                                                                                             |
| `WABBAJACK_IGNORE`                    | All files in this folder will be ignored by Wabbajack and therefore not be put into into the`.wabbajack` file. | Useful for tools or other things outside a mod you don't want/need reproduced on a users machine. Handle with care since excluded stuff can potentially break a setup.\* |
| `WABBAJACK_INCLUDE_SAVES`             | When this file exists Wabbajack will include your save files in the`.wabbajack` file.                          | This will remove previous savefiles when the list gets installed as an update.                                                                                           |
| `WABBAJACK_NOMATCH_INCLUDE_FILES.txt` | All files listed in this file will be included in the`.wabbajack` file.                                        | Every file needs to be in the same folder as the tag file. Every file need to be written into a new line. Every file needs to be added with its file extension.          |
| `WABBAJACK_IGNORE_FILES.txt`          | All files listed in this file will be ignored by Wabbajack and not included in the`.wabbajack` file.           | Every file needs to be in the same folder as the tag file. Every file need to be written into a new line. Every file needs to be added with its file extension.          |

\*It will finish the installation of a modlist, but the installed list might not run if you excluded a crutial part of it.

### Multiple MO2 Profiles

Wabbajack will normally ignore every other profile besides the active profile in your MO2 instance, but you might have more than one profile that you would like to include. In this case, you can create a `otherprofiles.txt` file in your main profile folder and write the names of the other profiles (1 per line) in it.

**Example**:

Profiles: `Main`, `Performance` (`Main` is the main profile)

contents of `MO2\profiles\SFW\otherprofiles.txt`:

```txt
Performance
```
