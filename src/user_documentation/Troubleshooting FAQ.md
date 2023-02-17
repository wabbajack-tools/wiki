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
> Please install/repair WebView2 by following the answer in this link:
> <https://superuser.com/questions/1751709/how-to-reinstall-microsoft-edge-webview2-runtime>
>
> **Repair your windows installation**
>
> Wabbjack is built using various libraries made by Microsoft and some of them require core functions of Microsoft Windows to be present that might get removed when people use debloaters or custom Windows 10/11 ISOs to install Windows. So please repair your windows if you ever have run such a deblaoter software/script.

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
