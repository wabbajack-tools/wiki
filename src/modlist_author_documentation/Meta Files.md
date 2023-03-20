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

### `directURL`

`.meta` files for sites that don't require logins are handled via the `directURL=link` tag. Archives with such `.meta` files will be automatically downloaded.

```ini
[General]
directURL=https://skse.silverlock.org/beta/skse64_2_00_20.7z
installed=true
```

### `manualURL`

`.meta` files for sites that require the user to manually navigate and download the file and, in some cases, log in, are handled in the following way. This option is recommended for LoversLab due to frequent outages and other issues with their automated API downloads.

```ini
manualURL=https://foo.bar.bz/someFile.zip
prompt=Please download the second file on this page
```

> **Note**
> Using `manualURL` makes it impossible for the WJ list validator to check files with this tag in regards to their uptime, so it falls to you to listen to user reports and verify regularly that the correct file still exists at the source you have linked.

### IPS4 sites

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

-   `ips4Site` - the site name for this download, currently this can only be `Vector Plexus` or `Lovers Lab`
-   `ips4Mod` - the number part of the URL, which in this case is `11116`
-   `ips4File` - the name of the file after is has finished downloading (removing any extra text added by windows)

So for the example file above, our `.meta` would be:

```ini
[General]
ips4Site=Lovers Lab
ips4Mod=11116
ips4File=WABBAJACK_TEST_FILE.zip
```

> **Note**
> This still uses LoversLab as the example but because LoversLab has a tendency to break it's API we highly recommend not using this meta option for LoversLab and using `manualURL` instead. The same goes for attachment files on LoversLab.

> **Note**
> Due to issues related to domain registration for VectorPlexus (URL was moved to www.vectorplexis.com) and unexpected downtimes, we advise modlist authors to use mirrors provided by mod authors instead to ensure maximum uptime for your modlist.

## Reference Table

| Site                                      | Requires Login | Requires Whitelist Entry | Notes                                                                                                                                                                     |
| ----------------------------------------- | -------------- | ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [LoversLab](https://www.loverslab.com/)   | Yes            | No                       | IPS4 Site, The API is not reliable so use of `manualURL` strongly recommended.                                                                                            |
| [VectorPlexus](https://vectorplexis.com/) | Yes            | No                       | IPS4 Site, The API isn't unreliable but due to some issues of domain registration and unexpected downtimes we recommend using mirrors provided by the mod authors instead |
| [ModDB](https://www.moddb.com/)           | No             | No                       | Downloads can be very slow                                                                                                                                                |
| [Patreon](https://www.patreon.com/)       | No             | Yes                      | Only public downloads, pay-walled downloads cannot be downloaded                                                                                                          |
| [GitHub](https://github.com/)             | No             | No                       |                                                                                                                                                                           |
| [Google Drive](https://drive.google.com/) | No             | Yes                      |                                                                                                                                                                           |
| [MEGA](https://mega.nz/)                  | No (Optional)  | Yes                      |                                                                                                                                                                           |
| [Mediafire](https://www.mediafire.com/)   | No             | Yes                      |                                                                                                                                                                           |
| [Dropbox](https://www.dropbox.com/)       | No             | Yes                      |                                                                                                                                                                           |
| [Yandex Disk](https://disk.yandex.com/)   | No             | Yes                      |                                                                                                                                                                           |
