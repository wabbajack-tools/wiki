# Supported Games and Mod Managers

## Supported Games

If you own a game on this list on the Epic Games Store, and the store isn't listed as supported, please get in touch on [Discord](https://discord.gg/wabbajack), so you can help us make Wabbajack support those versions as well.
This is needed, since the EGS has no public database of its game IDs.

| Game                        | Platform                     | Versions                            | Notes                          |
|-----------------------------|------------------------------|-------------------------------------|--------------------------------|
| Cyberpunk 2077              | Steam, GOG                   |                                     | Experimental                   |
| Darkest Dungeon             | Steam, GOG, Epic Games Store |                                     | Experimental                   |
| Dishonored                  | Steam, GOG                   |                                     | Experimental                   |
| Dragon's Dogma: Dark Arisen | Steam, GOG                   |                                     | Experimental                   |
| Dragon Age 2                | Steam, Origin                |                                     | Experimental                   |
| Dragon Age Inquisition      | Steam, Origin                |                                     | Experimental                   |
| Dragon Age Origins          | Stean, GOG, Origin           |                                     | Experimental                   |
| Enderal                     | Steam                        |                                     |                                |
| Enderal Special Edition     | Steam                        |                                     |                                |
| Fallout 4                   | Steam                        |                                     |                                |
| Fallout 4 VR                | Steam                        |                                     |                                |
| Fallout 3                   | Steam, GOG                   | Normal and GotY                     | Platform-locked*               |
| Fallout New Vegas           | Steam, GOG                   | Normal and region locked RU version | Platform-locked*               |
| Karryn's Prison             | Steam                        |                                     | Experimental                   |
| Kerbal Space Program        | Steam, GOG                   |                                     | Experimental                   |
| Sims 4                      | Steam                        |                                     | Experimental                   |
| Stardew Valley              | Steam, GOG                   |                                     | Experimental, Platform-locked* |
| Terraria                    | Steam                        | tModloader                          | Experimental                   |
| TES Morrowind               | Steam, GOG                   |                                     |                                |
| TES Oblivion                | Steam, GOG                   | Normal and GotY                     | Platform-locked*               |
| TES Skyrim                  | Steam                        |                                     |                                |
| TES Skyrim Special Edition  | Steam, GOG                   |                                     | Platform-locked*               |
| TES Skyrim VR               | Steam                        |                                     |                                |
| The Witcher                 | Steam, GOG                   | Enhanced Edition                    | Experimental                   |
| The Witcher 3               | Steam, GOG                   | Normal and GotY                     | Experimental, Platform-locked* |
| Kingdom Come: Deliverance   | Steam, GOG                   |                                     | Experimental                   |
| Mechwarrior 5: Mercenaries  | Epic Games Store             |                                     | Experimental                   |
| No Man's Sky                | Steam, GOG                   |                                     | Experimental                   |

**Experimental**:

A Mod Organizer 2 (MO2) plugin called [Basic Games Plugin](https://github.com/ModOrganizer2/modorganizer-basic_games) enables the easy creation of new game plugins for non BGS games. This is still fairly experimental in both MO2 and Wabbajack and doesn't work perfectly in all games yet.

Some like Mechwarrior 5 use a complete new method of creating a modlist, that **will**
require slightly more manual steps after Wabbajack is done compared to most modlists using MO2

**Platform-locked***:

Games marked as platform-locked have differences in core game files between different platforms, making modlists "locked" to the version they are built for.
For clear per modlist compatibility information please consult the readmes and other documentation provided by the authors of those lists. (Some will work with multiple platforms, BUT that is NOT the default.) Please keep in mind, that for some games we might not know yet if they will cause issues so only the ones we 100% know have issues are marked as such.

## Supported Mod Mangers

As of the time this is being written the only officially supported mod manager is [Mod Organizer 2](https://github.com/ModOrganizer2/modorganizer/releases).

There is however the option for creating a wabbajack installer that simply recreates a whole folder by linking individual files to their originally sourced downloads.  
Modlists created with this option will require more manual instructions for where users will be required to copy/move those files, but it is a way to allow modlists for games like Dishonored, the small demo for that system or Mechwarrior 5 that don't have Mod Organizer 2 support. You can learn about this option [here](nat), for more info and guidance join the [Discord](https://discord.gg/wabbajack).
