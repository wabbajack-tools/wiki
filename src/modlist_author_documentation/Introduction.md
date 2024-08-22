# Introduction

Modlist Creation--or Compilation, as we call it--is a trial and error process. You will likely get a decent amount of compilation errors in the beginning and have to spend some time fixing them before your first compilation succeeds. After that you can do incremental builds which take significantly less time and have close to zero errors compared to your first build. In short, the main requirement is an eagerness to learn and a willingness to fail a few times while doing so.

## Requirements

Wabbajack requires that you create your Modlist using a [**portable**](Compilation%20Issues%20FAQ.html#portable-instances) instance of Mod Organizer 2. This is a **hard requirement**. Wabbajack won't work with Vortex, Kortex, Wyre Bash, Nexus Mod Manager, Oblivion Mod Manager or any other mod manager--not even Mod Organizer 1 (at least not without severe drawbacks and complications).

There is an option for compiling free of any mod manager, but this has not been tested deeply and requires more manual setup on the user-end compared to the fully automated, default method for compiling a modlist. Documentation for this method can be found at [Native-Game-Installer - (Installers not using MO2)](<Native-Game-Installer%20-%20(Installers%20not%20using%20MO2).md>).

Do note that your installed Mods folder needs to be inside of your MO2 installation, so Wabbajack can replicate it.
Your Downloads can be anywhere else, but still recommended to be outside any [Windows protected folders](<../user_documentation/Installing%20a%20Modlist.md>).

In addition to using a portable MO2 installation (or using the "Native Game Installer" method), mod authors are encouraged to use the recommended workflow for modlist development described in the following sections.
