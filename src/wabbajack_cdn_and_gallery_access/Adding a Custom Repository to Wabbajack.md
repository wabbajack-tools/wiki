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

Set the name of the file to `modlists.json`. It can be named anything, but it's nice to have some uniformity.

Now fill out all the various fields for your modlist, you can use this text as a template:

```json
[
  {
    "$type": "ModListMetadata, Wabbajack.Lib",
    "title": "My Modlist",
    "description": "Best thing since sliced bread",
    "author": "<any name you want to show up in the UI>",
    "maintainers": [
      "github/<your github name>"
    ],
    "game": "skyrimspecialedition",
    "tags": [
      "testing",
      "<any tags you want in the UI, each in its own string"
    ],
    "nsfw": false,
    "image_contains_title": false,
    "force_down": false,
    "links": {
      "$type": "Links, Wabbajack.Lib",
      "image": "<link to an image to show in the UI>",
      "readme": "<link to your readme for your modlist>",
      "download": "https://authored-files.wabbajack.org/Halgaris Helper.wabbajack_29d245c9-5f7f-4394-b600-a22e43427337",
      "machineURL": "machineURL",
      "discordURL": "<your discord link here>"
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
    "version": "1.0"
  }
]

```

**Notes on the metadata above:**

* Download Metadata - The contents of `download_metadata` can be found in the `.wabbajack.meta.json` file that's created by Wabbajack after you create compile your list.
* MachineURL - no strings, punctuation or special characters allowed (except underscore `_`). This name must be unique to this repository
* `image_contains_title` - set to `true` if your gallery image contains the modlist title
    *  _Note:  Image URL MUST be in the following format:_ `https://raw.githubusercontent.com/user/repository/main/nameofimagefile.png`  _Obtainlable by clicking the 'Download' button next to the image._
* `force_down` - something broken in your list? Set this to true to disable it in the UI
* `nsfw` - you *must* set this to true if your modlist contains explicit sexual acts. If your list just contains nudity, then you don't have to set this to true.

Once you're satisfied with the contents of the metadata, [validate your json](https://jsonlint.com/) and click `Commit new file` afterwards.

![Step5](https://user-images.githubusercontent.com/654621/161399933-2012365b-0891-45f3-a21d-14a72dca1247.png)

## Adding your repository

Now you need to add your repository to the Wabbajack master repository list. View your `modlists.json` file in GitHub, click on the `Raw` button and copy the URL on the page that opens.

![Step6](https://user-images.githubusercontent.com/654621/161399961-bc0cdb28-74d8-4c69-8cb0-11863083bee1.png)

Now navigate to this file: <https://github.com/wabbajack-tools/mod-lists/blob/master/repositories.json> and select the `Edit` button.

![Step8](https://user-images.githubusercontent.com/654621/161399990-d3d1a66a-ac50-4a6d-9af5-4420eaea4cc3.png)

Add a new line (don't forget the comma after the last line) and give your repository a unique name, and paste in the link you copied above.

_Note:  URL MUST be in the following format:  https://raw.githubusercontent.com/user/repository/main/modlists.json.  Obtainlable by opening the modlists.json file clicking the 'Raw' button.  Copy the URL on the page that opens._

![Step9](https://user-images.githubusercontent.com/654621/161400507-40238db1-4ec3-4599-8082-ba961ac79b1b.png)

Click "Create a new Branch..." and "Propose Changes".

![Step10](https://user-images.githubusercontent.com/654621/161400527-669820df-7147-419d-b903-4eff6eeddb9c.png)

On the next page, click "Create Pull Request".

![Step10](https://user-images.githubusercontent.com/654621/161400531-0cae7ffd-4039-4f95-9f16-ce6e1b3b9e3d.png)

Probably best at this point to put a link to the Pull Request you just created in the [Wabbajack Discord](https://discord.gg/wabbajack) but otherwise we'll probably see it soon and take a look. One the PR is merged, your modlist should show up in the Wabbajack UI.

### Verifying Pull Requests

**This section is importat for everyone with merge permissions!**

**General Information:**

We all know how frequently in the past a broken .json file has caused us headaches like a broken gallery in the app and on the website. To fix this the github Validation for modlist repositories has been updated. It now also validates the repositories.json AND the there linked .json files.

The test will run every 4 hours, pull request and commit made to the mod-lists repository.

To check past runs or trigger a new run on the main repository (in case the website and app gallery are broken and you need to find the issue) go to the [Github Actions Tab](https://github.com/wabbajack-tools/mod-lists/actions/workflows/validation.yml)

![run_validation_on_master](assets/run_validation_on_master.webp)

**Merging Procedure:**

Before merging older pull requests it is recommended to run the validation again **even if they are validated**, because the linked json file could have been broken or deleted over time or a previously broken json got fixed already.  

1. Go to the Details page of the Validation run:  
  ![show_validation_run_details](assets/show_validation_run_details.webp)
2. Re-run all jobs:  
  ![re-run_all_jobs](assets/re-run_all_jobs.webp)
3. When the run is successful the pull request can be merged or when it was just a normal run then the gallery is in perfect condition.  
If the run is unsuccessful you can find the reason for the test failing in the log under the test section:  
![failed_run_example](assets/failed_run_example.webp)  
In this example the error was a missing `,` in the .json file of the repository planned to be merged.

## Common Errors

When uploading a new list to your repository, there are several errors that you may encounter.

### You do not have access to this list

If you get this error, chances are the list's definition does not include your *Github username* in the list of maintainers. Remember to prefix your username with `github/` so if your username is `JohnDoe` then the maintainer list should have an entry of `"github/JohnDoe"`.

### Namespaced list required

Lists names provided in the UI should be namespaced with the repo name. The format in of the `machineURL` entry in Wabbajack is `<repo>/<list-name>`. So if you have a repo named `JohnsLists` and your list that you are updating is `JohnsSkyrimMakeover` then the machineURL field in WJ's compiler UI should be set to `JohnsLists/JohnsSkyrimMakeover`.

### 404 Error when updating a `wj-featured/` list

The repo `wj-featured` is managed by the wabbajack team, you'll need to request membership to the WJ modlist team group, or just go and make your own repo.

### 404 errors when uploading lists

You probably forgot to set the permissions on your Github Personal access token, verify that's all setup correctly as per [these instructions](https://github.com/wabbajack-tools/wiki/wiki/Getting-CDN-Access)
