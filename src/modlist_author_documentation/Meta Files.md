# Meta Files

_Read [Everything comes from somewhere](Pre-Compilation.md#everything-comes-from-somewhere) first, as that section explains the basic concepts of meta files. This section focuses more on advanced cases, like using mods not hosted on Nexus mods._

## Introduction

You already know how `.meta` files should look for mods that come from Nexus Mods:

```ini
[General]
gameName=Skyrim
modID=3863
fileID=1000172397
```

This is the basic configuration for an archive that originates from Nexus Mods. You can get these types of `.meta` files through MO2 by using the **`Query Info`** context menu option in the Downloads tab.

Mods can also be hosted somewhere else, e.g., other modding sites like LoversLab, ModDB or file hosting services like Google Drive and MEGA. For a full table of all supported sites that Wabbajack can download from, see the section at the bottom of this page.

## Non-Nexus `.meta` Files

-   Every `.meta` file, no matter the site, has to start with `[General]`
-   `.meta` files are **case-sensitive**
-   The "Whitelist" Wabbajack uses to manage non-Nexus sources is available on [GitHub](https://github.com/wabbajack-tools/opt-out-lists/blob/master/ServerWhitelist.yml). You may have to create a Pull Request if you want to add a link to a file that we haven't checked and whitelisted yet.

### directURL

`.meta` files for sites that don't require logins are handled via the `directURL=link` tag. Archives with such `.meta` files will be automatically downloaded.

Example:
```ini
[General]
directURL=https://skse.silverlock.org/beta/skse64_2_00_20.7z
installed=true
```

#### Using directURL with Google Drive

`.meta` files pointing to Google Drive links should be using the following URL to be recognized properly: `https://drive.google.com/uc?id=<ID>&export=download`, where `<ID>` is replaced with the Google Drive ID.

Example:
```ini
[General]
installed = true
directURL = https://drive.google.com/uc?id=1RQl8ki73fgLnzBZn6EWjneuW4Dk8TUO_&export=download
```



#### How to get persistent Github URLs

- If there are releases, use them.
- If you need to "clone"/download the whole repository as a ZIP file do the following:
  - Click on the commit history:  
    ![image](https://github.com/user-attachments/assets/93676860-b399-4f09-953f-fc910f23ff18)  
  - Click on the button to browse the latest commit:
    ![image](https://github.com/user-attachments/assets/cb4cb9bc-9dda-4e9f-86dd-16d1c7153b68)
  - Make sure that you are browsing a commit by having "random" numbers and letters where normally a branch name would be and copy the download link (and download it):  
    (You can rename the zip & meta file to have the name you want BUT make sure to get the proper URL for the correct file first.)
    ![image](https://github.com/user-attachments/assets/f103de31-6f31-410c-b70e-d50f7835a280)




### manualURL

`.meta` files for sites that require the user to manually navigate and download the file and, in some cases, log in, are handled in the following way. This option is recommended for LoversLab due to frequent outages and other issues with their automated API downloads. Optionally, a prompt can be specified that will be shown to the user in the Wabbajack UI.

```ini
manualURL=https://foo.bar.bz/someFile.zip
prompt=Please download the second file on this page
```

> **Note**
> Using `manualURL` makes it impossible for the WJ list validator to check files with this tag in regards to their uptime, so it falls to you to listen to user reports and verify regularly that the correct file still exists at the source you have linked.

### IPS4 sites

> **Note**
> The support for this type of meta is currently not actively supported. And might be fully removed. 

In order to configure a `.meta` file for a IPS4 site, use the following format:

Let's say we're making a meta for a file found at `https://www.loverslab.com/files/file/11116-test-file-for-wabbajack-integration`

Start by downloading the file and noting its name once it's downloaded. If you've downloaded the file more than once, Windows may include `(1)` at the end of the filename, so you'll need to remove that part from the filename.

Now create a `.meta` file in this format:

```ini
[General]
ips4Site=<Site Name>
ips4Mod=<modID>
ips4File=<filename>
```

- `ips4Site` - the site name for this download, currently this can only be ~~`Vector Plexus` or `Lovers Lab`~~
- `ips4Mod` - the number part of the URL, which in this case is `11116`
- `ips4File` - the name of the file after is has finished downloading (removing any extra text added by windows)

So for the example file above, our `.meta` would be:

```ini
[General]
ips4Site=Lovers Lab
ips4Mod=11116
ips4File=WABBAJACK_TEST_FILE.zip
```

> **Warning**:
> This page still uses LoversLab as the example, because the logic is the same as with any supported ISP4 website, but because LoversLab has a tendency to break it's API we **disabled** using this meta option for LoversLab and people have to use `manualURL` instead. The same goes for attachment files on LoversLab.  

> **Note**:
> Due to unexpected downtimes in the past, we advise modlist authors to use mirrors provided by mod authors where possible instead of this implementation to ensure maximum uptime for your modlist.

## Reference Table

| Site                                      | Requires Login | Requires Whitelist Entry | Notes                                                                                                                        |
|-------------------------------------------|----------------|--------------------------|------------------------------------------------------------------------------------------------------------------------------|
| [Nexusmods](https://www.nexusmods.com)    | Yes            | No                       | See [Introduction](#introduction).                                                                                           |
| [LoversLab](https://www.loverslab.com/)   | Yes            | No                       | Only [manualURL](#manualurl) support.                                                                                        |
| [VectorPlexus](https://vectorplexis.com/) | Yes            | No                       | [manualURL](#manualurl) support. (Official (mod author made) mirrors **strongly** recommended.)                              |
| [ModDB](https://www.moddb.com/)           | No             | No                       | [directURL](#directurl) Support. Downloads can be very slow.                                                                 |
| [Patreon](https://www.patreon.com/)       | No             | Yes                      | [directURL](#directurl) Support. Only public downloads, pay-walled downloads cannot be downloaded.                           |
| [GitHub](https://github.com/)             | No             | No                       | [directURL](#directurl) Support. \*Please read [this](#how-to-get-persistent-github-urls) for repositories without releases  |
| [Google Drive](https://drive.google.com/) | No             | Yes                      | [directURL](#directurl) Support.                                                                                             |
| [MEGA](https://mega.nz/)                  | No (Optional)  | Yes                      | [directURL](#directurl) Support.                                                                                             |
| [Mediafire](https://www.mediafire.com/)   | No             | Yes                      | [directURL](#directurl) Support.                                                                                             |
| [Dropbox](https://www.dropbox.com/)       | No             | Yes                      | [directURL](#directurl) Support.                                                                                             |
| [Yandex Disk](https://disk.yandex.com/)   | No             | Yes                      | [directURL](#directurl) Support.                                                                                             |
| Direct file downloads                     | No             | Yes                      | [directURL](#directurl) Support.                                                                                             |
