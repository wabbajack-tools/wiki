# Post-Compilation


## So what now?

After a successful compilation, Wabbajack has completed its work and you may upload the created `.wabbajack` file to, say, the Nexus, share it with people, or just keep it for yourself as a backup. This section is for people who want to share their modlist with the community.

## Featured modlists

In the Wabbajack community we differentiate between _official_/_featured_ and _unofficial_ modlists. The former are curated modlists that comply with the criteria in [Criteria for 'Featured Mod List' status](../wabbajack_cdn_and_gallery_access/Criteria%20for%20'Featured%20Mod%20List'%20status.md) and have met the standards of the Wabbajack team. Official modlists are available in the main Wabbajack Gallery with no further user action required to find them, whereas unofficial modlists that come from custom repositories and are only visible when enabling the `Show Unofficial Lists` filter.

Official Modlists are required to have their own support Discord and often have 500-2500+ users depending on the game. Do note that these modlists receive regular updates and the authors put in a lot of work to deliver the best possible version of their modlist with each update.

## Readme readability

Managing a modlist can be tricky if you have never done it before. In the early days of Wabbajack we mostly relied on Google Docs READMEs and hosted all accompanying files on Google Drive while managing issues through the support channel on Discord. This system was later almost completely replaced through the valiant efforts of one of our developers: almost all new modlists use GitHub for managing and hosting readmes and other info.

GitHub was made for developers and is the site you are currently on. It mostly hosts source code for open source projects, such as Wabbajack, but can also be used for project management. Another strong point is Markdown support. This README you are currently reading is, like every other GitHub README, written in Markdown and rendered on GitHub.

On the topic of READMEs: you should create a good one.

It is not sufficient to just slap some install and MCM instructions in there. Your modlist might contain a thousand mods and offer hundreds of hours playtime, but it's no use if the user doesn't know what in Oblivion is going on and what's included in the modlist!

Example structure for a good README:

-   **Preamble**: Give a quick overview about what your modlist is about, your vision of the modlist, and also mention that it's a Wabbajack modlist (some might not know what Wabbajack is so link to this README)
-   **Requirements**: Simple list of requirements such as minimum CPU, GPU, RAM and most importantly: storage space. Also include a list of accounts the user needs such as a Nexus Mods, LoversLab, VectorPlexus or any other sites your modlist is using archives from
-   **Installation**: Installation instructions specific to your modlist. You can take a look at some of the modlists linked below as almost all of them use the same instructions with minor changes
-   **Important mods you should know about**: This is an important section you should not forget. Go in-depth on core mods and talk about _important mods the user should know about_. It can be overwhelming for the user to be thrust into a completely modded world without knowing at least a little about what's included.
-   **MCM**: If your modlist has MCMs (Mod Configuration Menus), as in Skyrim or Fallout 4, you should provide instructions on how to configure any MCMs that might need to be configured
-   **Changelog**: Should not be in the README and can be in a separate file called `CHANGELOG.md`--but make sure to create one! Good versioning is essential

Some modlists that host all their stuff on GitHub:

-   the OG GitHub Modlist: [Lotus](https://github.com/erri120/lotus)
-   [Keizaal](https://github.com/PierreDespereaux/Keizaal)
-   [Elder Souls](https://github.com/jdsmith2816/eldersouls)
-   [Total Visual Overhaul](https://github.com/NotTotal/Total-Visual-Overhaul)
-   [Serenity](https://github.com/ixanza/serenity)
-   [RGE](https://github.com/jdsmith2816/rge)
-   [Elysium](https://github.com/TitansBane/Elysium)

Other modlists opt to host all of their information on a dedicated website:

-   [The Phoenix Flavour](https://thephoenixflavour.com)
-   [Living Skyrim](https://www.fgsmodlists.com/living-skyrim)
-   [MOISE](https://www.fgsmodlists.com/moise)
-   [Dungeons & Deviousness](https://www.fgsmodlists.com/dd)
-   [Tales From the Northern Lands](https://eziothedeadpoet.github.io/Tales-from-the-Northern-Lands/)

## Modlist contents report

Do you want to check what's in your compiled WJ file?  
See our article [Wabbajack CLI](wabbajack_cli\Commands.md) how to access the commandline interface of Wabbajack.  
  
Use the command `wabbajack-cli.exe modlist-report -i "C:\modlist.wabbajack"`.

* Change the `"C:\modlist.wabbajack"` to the path location of your Wabbajack modlist compilation.  

A .html file will be generated, which you can then open and you will see what's being downloaded, inlined, and/or delta patched in the compilation file.
