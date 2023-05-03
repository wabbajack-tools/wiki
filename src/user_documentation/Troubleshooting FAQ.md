# Troubleshooting FAQ

This page is and will always be in development and update over time.

## Wabbajack Setup

### Wabbjack refusing to launch

- If you used Wabbajack before try the following:  
  > **Reset Your Wabbajack Installation**
  >
  >To completely reset your Wabbajack settings, start off by closing Wabbajack if it is open. Afterwards, press `Windows + R` on your keyboard and type in `%localappdata%`.
  >
  >You should see a Windows Explorer window pop-up; find and delete the folder called Wabbajack.

  **Important:** `%localappdata%` **NOT** `%appdata%` !!

  This will **NOT** affect any already installed lists or downloaded files.

- If have never used Wabbjack before  or the previous instructions didn't work try the following:  
  > **Manually Install Wabbjack**
  >
  > To manually install Wabbajack go to [the latest release](https://github.com/wabbajack-tools/wabbajack/releases/latest) and download both the `X.X.X.X.zip` (will be the latest version number instead of X.X.X.X) and the `Wabbajack.exe`.
  >
  > Go to a folder on one of your drives and create a folder called `Wabbajack` if you are using an existing folder make sure you emptied it before. Now copy the previously downloaded files into this folder.
  >
  > Extract the `X.X.X.X.zip` in a way that you have a folder called `X.X.X.X` (again the current version number) filled with the contents of the .zip archive.
  >
  > Now you should be able to run Wabbajack from the `Wabbajack.exe`

## Using Wabbajack

### Wabbajack shows a black screen when trying to X

> **Install/Repair WebView2**
>
> Use the official WebView2 Installer found [here](https://developer.microsoft.com/en-us/microsoft-edge/webview2/#download-section).
>
> ![WebView2 Installer](https://media.discordapp.net/attachments/666599178788536331/1095403884438098001/image.png)
>
> If the above fails please install/repair WebView2 by following the answer to a similar issue linked here:
> <https://superuser.com/questions/1751709/how-to-reinstall-microsoft-edge-webview2-runtime>
>
> **Repair your windows installation**
>
> Wabbjack is built using various libraries made by Microsoft and some of them require core functions of Microsoft Windows to be present that might get removed when people use debloaters or custom Windows 10/11 ISOs to install Windows. So please repair your windows if you ever have run such a deblaoter software/script.

### Wabbajack Modlists not loading or downloading

> **Conflicting Network Settings/Apps**
>
> `Killer Control Centre`/`Killer Intelligence Center` are at least 2 known apps that contain settings that break Wabbajack. This software is known to be likely bundled with Dell/Alienware laptops but also be related to Intel chipsets because it shows up in the Intel Driver Support app. To fix the issues they cause with Wabbajack you need to:
>
> - disable the Prioritization Engine
> - possibly need to disable Auto Bandwidth too
>
> At least that's what fixed it for the user that figured out this conflict and other users that had similar issues.

### Wabbajack Extraction Errors

> **Sanity Check Error**
>
> `[ERROR] (Wabbajack.InstallerVM) Sanity check error extracting`
>
> - If your system locale (language) is set to any langage not using latin-script letters (like english does) set your system language to english or any other latin-script language you can understand and the issue is likely fixed. (It has worked for some people in the past.)
> - Other possible reasons for this and workarounds or fixes are unknown at the time of writing this.

### BSOD (Bluescreen of Death) / PC Crash

> **SYSTEM_THREAD_EXCEPTION_NOT_HANDLED**
>
> - **Overclocking:** If you get this Bluescreen one of your Drivers is acting up, as a gamer most likely due to an unstable overclock. And the reason you are likely "only" crashing when using Wabbajack is because Wabbajack was written to use all your system resources at their most potenital, effectively stresstesting your hardware. And you might say "I am only using a GPU overclock, how would that effect Wabbajack ?" and the answer is, that Wabbajack uses your GPU for processing textures when installing modlists.
> - **Driver Issues:** If you didn't overclock your system the same principle applies only that one of your Drivers seems to be broken and should be repaired. More details on this can be found [here](https://helpdeskgeek.com/windows-10/how-to-fix-a-system-thread-exception-not-handled-bsod/).

### Don't run as Admin!

> **"But I am not running it as Admin"**
>
> You might not have choosen to explicitly run Wabbjack with admin priviliges, BUT you either are running Wabbajack with [UAC](https://en.wikipedia.org/wiki/User_Account_Control) disabled which makes it so essentially every program is always executed as admin.  
> If it is only disabled you can simply enable UAC like this:
> ![UAC](https://media.discordapp.net/attachments/666599178788536331/1041355863832678500/image.png?width=1396&height=671)
> After doing this restart your PC for the change to be active.
>
> If you have a customised installation of Windows and cannot access UAC try the following:
>
> > 1. Create a basic user account (Accounts -> Other users then add other user, click on Users, more actions and create new user)
> > 2. Login to that account - start Skyrim to add the registry entries for that user
> > 3. Log back into your primary account
> > 4. Hold shift, right click the .exe which will give a "Run as different user" command
> > 5. Select your created basic user
> >
> > Wabbajack is not responsible for any issues arising from attempting to run the application on non-standard Windows installations.
