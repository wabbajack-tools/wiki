# Adding a Custom Repository to Wabbajack

This is a guide for how you can make your own custom repository for making your Mod Lists show up on the Wabbajack in app gallery as unofficial Mod Lists.  
This guide requires you to have already completed [Getting CDN Access](Getting%20CDN%20Access.md).

## Create a Github Repository

To start with, log into your Github Account and create a new repository by clicking the `+` next to your avatar:

![Step1](https://user-images.githubusercontent.com/654621/161399306-8b3aa14a-9939-4440-9823-5ba0aa95e398.png)

On the next page, give the repository a name, make sure it's set to public, and have Github create a `README.md` by default. Click `Create repository`

![Step2](https://user-images.githubusercontent.com/654621/161399316-df090b1b-c52c-45a1-a175-b432dc0644d1.png)

On the next page, click `Add file`

![Step3](https://user-images.githubusercontent.com/654621/161399676-0ce978c3-cb46-4bae-ad56-7fc97f5850a1.png)

Set the name of the file to `modlists.json`.

Next you'll need to fill out all the fields for your modlist.

## Filling out the fields of modlists.json
Below is a template for modlists.json, and an overview of all the fields that should be filled in accordingly.

### Title

The name of your modlist.

Example: *John's Skyrim Makeover*

### Description

A brief summary of what your modlist has on offer.

Example: *A lightweight visual makeover of Skyrim that sticks to the original look!*

### Author
Your (nick)name.

Example: *JohnDoe*

### Maintainers

This should include your GitHub name and any additional contributors that will be publishing your modlist. Needs to be prefixed with "github/".

Example: *github/JohnDoe*

### Game

The name of the game you're targeting with this modlist. Using a game that's not on the gallery yet? Wabbajack first needs to support it. You can find the list of game names Wabbajack supports [by clicking here](https://github.com/wabbajack-tools/wabbajack/blob/main/Wabbajack.DTOs/Game/Game.cs).

Example: *skyrimspecialedition*

### Tags

You can use any tags that are on the allowed list [found here](https://github.com/wabbajack-tools/mod-lists/blob/master/allowed_tags.json). Other tags will not show up on the Wabbajack gallery.

Example: *SFW*, *Steam*, *Vanilla+*

### NSFW

You need to set this to true if your modlist contains explicit sexual content added by mods (sex frameworks). If your list just contains nudity, there is no need to set this to true.

### Image Contains Title

This determines whether your list name is shown without any mouse hover in the gallery. You can use this if your modlist image does not contain the name of your modlist, but we encourage you to put it in the image instead of using this.

### Force Down

If you want to disable your list from being downloadable in the gallery, setting this to true will force the modlist to be 'under maintenance' in the gallery.

### Links

#### Image

A raw link to an image hosted on GitHub, but with the 'refs/heads' part in the URL removed since this has additional caching on it.

The image should meet the following criteria:
* 16:9 format - for example a resolution of 1600x900 or 1920x1080
* At or below 1MB in size
* Supported formats: WebP (preferred), PNG, JPG

Example: *https://raw.githubusercontent.com/Dylan-Perry/dp-modlists/main/wj_thumbnail-web.webp*

#### Readme

A link to the readme of your modlist containing documentation on how to install the modlist.

It's fairly easy to make a GitHub readme in Markdown format, but custom websites are fine too.

#### Download

A link where the Wabbajack file of your modlist can be downloaded. It should be uploaded to the Wabbajack CDN, instructions on how to set this up are in the Getting CDN Access portion of this website.

Example: *https://authored-files.wabbajack.org/Halgaris Helper.wabbajack_29d245c9-5f7f-4394-b600-a22e43427337*

#### Machine URL

The modlist name as a unique identifier. No special characters allowed (except underscore `_`).

This name MUST be unique to this repository.

Use PascalCase - the name of your modlist without spaces, with capital letters for each word. So "John's Skyrim Makeover" becomes 'JohnsSkyrimMakeover'.

Example: *JohnsSkyrimMakeover*

#### Discord URL

A link to a support server or forum where users can contact you or find others using your modlist.

Example: *https://discord.gg/wabbajack*

### Download Metadata

You should copy the contents of the metadata Wabbajack puts out in the `.wabbajack.meta.json` file next to the .wabbajack file after compilation here.

### Version

The version in [semantic format](https://semver.org/). Other formats are not allowed!

Example: *1.0.0*

### Full template (adjust accordingly)

```json
[
  {
    "$type": "ModListMetadata, Wabbajack.Lib",
    "title": "Johns Skyrim Makeover",
    "description": "A complete visual makeover of Skyrim while sticking to the original system requirements!",
    "author": "JohnDoe",
    "maintainers": [
      "github/JohnDoe"
    ],
    "game": "skyrimspecialedition",
    "tags": [
      "SFW",
      "Steam",
      "Vanilla+"
    ],
    "nsfw": false,
    "image_contains_title": false,
    "force_down": false,
    "links": {
      "$type": "Links, Wabbajack.Lib",
      "image": "https://raw.githubusercontent.com/Dylan-Perry/dp-modlists/main/wj_thumbnail-web.webp",
      "readme": "https://keizaal.github.io/Keizaal/",
      "download": "https://authored-files.wabbajack.org/Halgaris Helper.wabbajack_29d245c9-5f7f-4394-b600-a22e43427337",
      "machineURL": "JohnsSkyrimMakeover",
      "discordURL": "https://discord.gg/wabbajack"
    },
    "download_metadata": {
      "$type": "DownloadMetadata, Wabbajack.Lib",
      "Hash": "e1+K7eJbDJw=",
      "Size": 0,
      "NumberOfArchives": 14,
      "SizeOfArchives": 135206078,
      "NumberOfInstalledFiles": 1311,
      "SizeOfInstalledFiles": 336453775
    },
    "version": "1.0.0"
  }
]

```

Once you're done with the contents here, [validate your JSON](https://jsonlint.com/) and click `Commit new file` afterwards.

![Step5](https://user-images.githubusercontent.com/654621/161399933-2012365b-0891-45f3-a21d-14a72dca1247.png)

## Adding your repository

Now you need to add your repository to the Wabbajack master repository list. View your `modlists.json` file in GitHub, click on the `Raw` button and copy the URL on the page that opens.

Then go to [The Wabbajack mod-lists issues page](https://github.com/wabbajack-tools/mod-lists/issues) and click New Issue, where you will see this popup:

![Step6](https://github.com/user-attachments/assets/a6c9f5da-240b-41d8-a1fd-3ba17daae569)

Click "Submit a new Modlist Repository"

Follow the instructions on the page that pops up

You will now see this page :

![Step7](https://github.com/user-attachments/assets/bd076d7a-c711-4fed-aee3-be725b266e2a)

The bot will reply to your created "issue" with any problems it encountered in your modlist.json, as per the image, if you fix the issue it highlighted, then comment "fixed" in a reply, it will check again.

This will continue until there are no problems, then it will highlight it for a maintainer to merge the request.


## Common Errors

When uploading a new list to your repository, there are several errors that you may encounter.

### You do not have access to this list

If you get this error, chances are the list's definition does not include your *Github username* in the list of maintainers. Remember to prefix your username with `github/` so if your username is `JohnDoe` then the maintainer list should have an entry of `"github/JohnDoe"`.

### Namespaced list required

Lists names provided in the UI should be namespaced with the repo name. The format in of the `machineURL` entry in Wabbajack is `<repo>/<list-name>`. So if you have a repo named `JohnsLists` and your list that you are updating is `JohnsSkyrimMakeover` then the machineURL field in WJ's compiler UI should be set to `JohnsLists/JohnsSkyrimMakeover`. This only needs to be done within Wabbajack itself - the machineURL entry of the modlists within your GitHub repository does not need the repository itself as a prefix.

### 404 Error when updating a `wj-featured/` list

The repo `wj-featured` is managed by the wabbajack team, you'll need to request membership to the WJ modlist team group, or just go and make your own repo.

### 404 errors when uploading lists

You probably forgot to set the permissions on your Github Personal access token, verify that's all setup correctly as per [these instructions](https://github.com/wabbajack-tools/wiki/wiki/Getting-CDN-Access)
