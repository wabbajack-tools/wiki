# Criteria for 'Featured Mod List' status

The general opinion of the Wabbajack project, post-decentralization, is that any well managed, well curated list should be valid for "featuring in the UI". This is a rather general and subjective statement, so instead of writing down the minimum requirements for a list to be accepted this is a list of known reasons why a list *will* be rejected.

## Rejection Reasons

### Pay-walled mods

No mods through Wabbajack should ever be paywalled. Free logins to patreon that then download files are allowed. Logins to 3rd party sites that have subscriptions are allowed, but a user should *never* be required to buy a non-game studio product to install a modlist. Downloadable content for the game is a fine requirement, a 3rd party paywalled mod is not. Please refer to the wabbajack monetization policy for more information.

### Users not required to downgrade

Users must be able to install your list from the latest version from steam (or any other storefront that your list supports). We will not grant featured status to any list that requires users to manually downgrade to install the list. Wabbajack has built-in facilities to auto downgrade via the "Stock Game Folder" take advantage of this.

*If the game updated while an author is busy with IRL obligations then we won't remove the featured status as long as the proper support for people to get the list running is provided or the author forces the list into maintenance mode until the next update.*

### Users shouldn't modify anything in their base game installation

On the note of downgrading, users should be able to install your list, regardless of any other modlist they have installed before or after your list.
This is primarily because people are more likely than not to end up running multiple modlists, and possibly their own modded setup on these games, so keeping the game directory clean is important to avoid issues. 

This is a strict requirement for the following games;
- Skyrim Special Edition
- Fallout 4
- Starfield

Note: For Skyrim lists, due to the difference between 'Rare Curios' sourced from steam and from the creation club store in game. It is required for ease of wabbajack support (and users) that featured lists use the in game "lower case" curios file.

For other and/or non-Bethesda games, it may not be possible to get them to function with MO2's VFS for game folder changes, so while it is still recommended, it is not required.

### Custom patching required

For Bethesda games your list **must** have custom patching as required. Conflicts, issues, and bugs must be resolved as appropriate through patching. Merely running synthesis or any automated patching suite is insufficient.

Non-bethesda games are required to patch as appropriate and possible for the modlist. 

### Modlists must have "Open Permissions"

Your modlist must allow other users to fork, modify and re-upload your modlist as per the Wabbajack [License](https://github.com/wabbajack-tools/wabbajack/blob/main/LICENSE.txt). This does *not* mean that you have to support such modifications, and the forking user should rename the list.

### User support required

Featured lists are required to provide technical support to users regarding the modlist without charging or paywalling. The modlist author must provide a place where users can report bugs, issues, and crashes where the user will recieve a reasonably timely response regarding their issue. Discord, or any other form of "live support," is not a requirement to be featured.

Modlist authors are not required to provide support regarding:

- User specific hardware, software, or basic computer usage problems
- Bugs, crashes, and issues present in the base game
- Gameplay guidance
- User's refusal to read provided instructions
- Users that violate the rules of the modlist author's support server

### If you fork a list, you must not advertise via their name unless given permission to do so

If you fork "Bill's Skyrim" you cannot name your list "Better Bill's Skyrim". Make your own name, make your own community, unless you ask the original author permission first.

### Written guides require the original author's participation

We will not grant featured status to a wabbajack of a written guide without the original author being a member of the development team. Mere permission is not good enough. Forks can be granted featured status, but they must be separate from the original written guide.

### Continuity of uptime and support

Your modlist must be present, functional, and available on the wabbjack UI as an unofficial list and supported for at least 30 days before it will be considered for featured status. You do not need to reach a specific number of downloads. 

### Allowed uploads and inlines

Your modlist cannot rely on files uploaded to the CDN that you do not have permission to rehost, this also applies to Nexusmods' policy on what is allowed to be uploaded on their platform. This also applies to inlining ( including files directly in the Wabbajack file ), as that is a form of rehosting.

Examples of outputs that are allowed to be uploaded to the Wabbajack CDN:
- Dyndolod Output
- Xlodgen Output
- Texgen Output
- Grasscache
- Bodyslide Output
- Nemesis/Pandora Output

Examples of outouts that are *not* allowed to be uploaded to the Wabbajack CDN:
- Parallaxgen Output
- VRAMR Output

These two tools provide modified textures of existing mods, therefore they are not substantially transformative, and would be considered rehosting of other authors work.

For those types of outputs that are not allowed to be uploaded, you will need to use Wabbajack's automatic delta-patching functionality.

This list is not exhaustive, when in doubt refer to Nexusmods' policy on what is allowed to be uploaded to their platform, as that will be mirrored in Wabbajacks CDN in most cases.

If you have specific permission to include or reupload a mod authors work or specific other content, then please provide proof that you have permission to do so from the creator.

### Nexus modpage Donation Points

- Modlists (Collections, Wabbajack, Nolvus, etc) are allowed one mod page for modlist specific files (tool outputs, list specific patches). This page is eligible for Donation Points.

- Mods that authors create for their modlist that are not usable outside of the modlist must be hosted on this one mod page and not split across multiple pages.

- Mod pages that only include 3rd party modlist installers are the equivalent of a Collection page and thus are not eligible of Donation Points.

- This does not include mods made for a list which are both usable outside of the list and presented to be used as such.

## Applying to get featured

When you think your list brings enough quality in the list itself, its documentation and the support provided then you can request a review of your list in the issues of the [Requests & Reports](https://github.com/wabbajack-tools/Requests-Reports/issues) repository by opening a new issue. There you will get open responses if we need any additional data about the list or replies to why the list can't be featured yet. We will not review lists for featured that do not request a review.

## Reporting lists

In the [Requests & Reports](https://github.com/wabbajack-tools/Requests-Reports/issues) repository you can also, as the name implies, report modlists that are breaking the rules or that you think should get re-reviewed. 
