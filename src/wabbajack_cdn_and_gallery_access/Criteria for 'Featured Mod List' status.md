# Criteria for 'Featured Mod List' status

The general opinion of the Wabbajack project, post-decentralization, is that any well managed, well curated list should be valid for "featuring in the UI". This is a rather general and subjective statement, so instead of writing down the minimum requirements for a list to be accepted this is a list of known reasons why a list *will* be rejected.

## Rejection Reasons

### Manual downloads outside of Wabbajack

Wabbajack has a `manualURL=` .meta directive that will instruct the user to download an install a file via the in-app browser. There should never be a reason for a user to us a browser from outside of Wabbajack. There should never be a step that requires the user to install a mod by hand.

There is an exception made here for lists that do not enable ENBs by default, but leave that as a manual option by the user. If your list has a optional ENB, it is recommended that you configure WJ to download the ENB files but not install them, and let the user copy them manually.

### Pay-walled mods

No mods through Wabbajack should ever be paywalled. Free logins to patreon that then download files are allowed. Logins to 3rd party sites that have subscriptions are allowed, but a user should *never* be required to buy a non-game studio product to install a modlist. Downloadable content for the game is a fine requirement, a 3rd party paywalled mod is not.

### Skyrim should auto-downgrade

If your list uses Skyrim 1.5.97, it should expect the user to have a unmodified copy of Skyrim. To avoid confusion we will not accept any list that requires the user to downgrade manually. Wabbajack has built-in facilities to auto downgrade via the "Stock Game Folder" take advantage of this.

### Modlists must have "Open Permissions"

Your modlist must allow other users to fork, modify and re-upload your modlist as per the Wabbajack [License](https://github.com/wabbajack-tools/wabbajack/blob/main/LICENSE.txt). This does *not* mean that you have to support such modifications, and the forking user should rename the list.

### If you fork a list, you must not advertise via their name unless given permission to do so

If you fork "Bill's Skyrim" you cannot name your list "Better Bill's Skyrim". Make your own name, make your own community, unless you ask the original author permission first

### Do *not* opt-in to Donation Points on the nexus for files that are not generic to modding

If a file you put on the Nexus is only usable by Wabbajack (patches, auto-generated files, .wabbajack files, etc.) Do not opt-in to donation points on these files. This is at the request of the Nexus. Collections on Nexus Mods do not get donation points, we should play by the same rules. If a mod is generally useful to modders at large, feel free to opt-in.

## Applying to get featured

When you think your list brings enough quality in the list itself, its documentation and the support provided then you can request a review of your list in the issues of the [Requests & Reports](https://github.com/wabbajack-tools/Requests-Reports/issues) repository by opening a new issue. There you will get open responses if we need any additional data about the list or replies to why the list can't be featured yet. 

## Reporting lists

In the [Requests & Reports](https://github.com/wabbajack-tools/Requests-Reports/issues) repository you can also, as the name implies, report modlists that are breaking the rules or that you think should get re-reviewed. 
