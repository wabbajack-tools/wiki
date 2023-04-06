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
    "ModlistIsNSFW": false,
    "Source": "F:\\Wabbajack Modlists Maintenance\\Dishonored 1.1",
    "Downloads": "E:\\Wabbajack Modlist Maintenance\\.Download Folders\\Dishonored",
    "Game": "Dishonored",
    "OutputFile": "F:\\Wabbajack Modlists Maintenance",
    "ModListImage": "F:\\Wabbajack Modlists Maintenance\\Dishonored 1.1\thumbnail.png",
    "UseGamePaths": true,
    "UseTextureRecompression": false,
    "OtherGames": [],
    "MaxVerificationTime": "00:01:00",
    "ModListName": "Listname",
    "ModListAuthor": "AuthorName",
    "ModListDescription": "",
    "ModListReadme": "",
    "ModListWebsite": "",
    "ModlistVersion": "1.0.0.0",
    "PublishUpdate": false,
    "MachineUrl": "",
    "Profile": "",
    "AdditionalProfiles": [],
    "NoMatchInclude": [],
    "Include": [],
    "Ignore": [],
    "AlwaysEnabled": [],
    "Version": "1.0.0",
    "Description": ""
}
```

- "ModlistIsNSFW": 
  - Can and should be changed in the Wabbajack UI
- **"Source":** 
  - Must be set to the folder you want to compile (and that will contain this `.compiler_settings` file). 
- **"Downloads":** 
  - Should be set to the donloaded archives for the setup, can be changed in the UI.
- **"Game"**: 
  - Must be set on the game that's being compiled.
- **"OutputFile":** 
  - The path to where the compiled `.wabbajack` will be stored.
- **"ModListImage"**:
  - The thumbnail/cover image for the modlist, MUST be a local stored image.
- "UseGamePaths":
  - Just keep this setting as it is.
- "UseTextureRecompression": 
  - This feature should not be used for non Bethesda games. (and even with them it might need more testing)
- "OtherGames": 
  - If your game requires files from other WJ supported games that need to be installed, you can add them to this list. Very unlikely and in the current stage of our indexed files only really available for Bethesda Games to source base game files for their VR versions.
- "MaxVerificationTime":
  - Just keep this setting as it is.
- **"ModListName":** 
  - Name of your List, can later be changed in the UI.
- **"ModListAuthor":** 
  - Your name , can later be changed in the UI.
- "ModListDescription": 
  - Can be and should be changed in the UI.
- **"ModListReadme":** 
  - Mandatory link to a website(or Readme on sites like Github) with additional instructions, can be changed in the UI.  
- **"ModListWebsite":** 
  - Link to a custom website, can also link to the readme. 
- "ModlistVersion":  
  - Can be and should be changed in the UI.
- "PublishUpdate": 
  - Relevant for automatic updloads when your compiles are finished. Only available after you have access to the CDN and your list in a custom repository.
- "MachineUrl": 
  - Link to your list for the update funktion `repositoryName/machineUrl`.
- "Profile": 
  - Just keep this setting as it is. 
- "AdditionalProfiles": 
  - Just keep this setting as it is.
- "NoMatchInclude": 
  - Can be and should be changed in the UI.
- "Include": 
  - Can be and should be changed in the UI.
- "Ignore": 
  - Can be and should be changed in the UI.
- "AlwaysEnabled": 
  - Just keep this setting as it is.
- "Version": 
  - Can be and should be changed in the UI.
- "Description": 
  - See ModListDescription.

## Building Your Setup

Now you can go ahead and build your setup as needed.

## Opening Wabbajack to Compile the List

See the next chapter for further instructions.
