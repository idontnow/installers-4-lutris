You can add **Star Wars: DroidWorks** to your Lutris library on Lutris.net:

https://lutris.net/games/star-wars-droidworks/

**The Lutris installer file can be found on this repo for your own customization.**

**Manual Patching REQUIRED for Star Wars: DroidWorks:**

        
The game **REQUIRES**¹ a patch that Lutris cannot apply automatically (at least not in the Flatpak version).

**16-bit SecuROM patch** - .xdelta patch for playing without CD check (that is not compatible with modern version of Windows/Wine prefixes); requires xdelta and cannot be applied automatically in Flatpak version of Lutris.

        
Having said that, to allow the game to work properly, follow these steps:

**16-bit SecuROM patch**

  1.   Download/Install xdelta

    You can use your package manager (e.g., 'sudo apt install xdelta3')
  
  Helpful guide: https://command-not-found.com/xdelta3

  2.   Download the following .xdelta patch file from this repo

    droidworks_NOCD.xdelta - for global game version

  3.   Locate the game folder with the original game .exe file (Pit Droids.exe)
  
    It's in your game's Wine prefix: {{ game.prefix }}/drive_c/Games/Droidworks/DroidWorks.exe

  Example:
  
    /home/youruser/Games/star-wars-droidworks/drive_c/Games/Droidworks/DroidWorks.exe

  4.   Move the .xdelta patch file into the game folder

  Example:
  
    /home/youruser/Games/star-wars-droidworks/drive_c/Games/Droidworks/droidworks_NOCD.xdelta

  5.   Open a Terminal from the game folder and run the patching command
  
    xdelta3 -f -d -s [game.exe] [patch_file.xdelta] [game.exe]

  Example:
  
    xdelta3 -f -d -s "DroidWorks.exe" droidworks_NOCD.xdelta "DroidWorks.exe"

After that, the game should be patched for compatibility with modern Windows!
  

**TIPS & TRICKS / KNOWN ISSUES & SOLUTIONS**

This game may require manual tweaking in order to run properly, depending on your setup.
What helped in my case was enabling Gamescope inside the Lutris System options for the game. I used the Fullscreen (default) Window mode.
It is also known that this game "suffers from timing issues that cause the in-game clock to run slightly fast and the physics to malfunction (especially on inclines)". Forcing VSync to be ON remedies this issue, but does not fix it completely (https://www.pcgamingwiki.com/wiki/Star_Wars:_DroidWorks#Fix_color_depth).

**NOTE:** install.iss is an InstallShield setup component that allows to silently install the game in the background to a default directory.
A guide for making one yourself can be found here: https://docs.revenera.com/installshield24helplib/helplibrary/CreatetheResponseFile.htm
It is technically not required, and you may install your game with a custom one or without it at all if you wish.
If you do decide to deviate, be mindful that the default game paths need to be adjusted accordingly in your Lutris settings!


**FOOT NOTES**

¹The game MAY run and play without a patch, but that would at least require additional tweaking of the 16-bit SafeDisc DRM for compatibility with modern versions of Windows (https://www.pcgamingwiki.com/wiki/Star_Wars:_DroidWorks#cite_note-3) which is way outside the scope of my knowledge. Even if you could get that to work, the game would still prompt you to insert your game CD before it plays, and stop you from playing whenever you eject the CD, which can get annoying if you don't want to keep the disc spinning in your physical drive or mounted virtually all the time.
