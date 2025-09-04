You can add **Star Wars: Pit Droids** to your Lutris library on Lutris.net:

https://lutris.net/games/star-wars-pit-droids/

**The Lutris installer file can be found on this repo for your own customization.**


**Manual Patching REQUIRED for Star Wars: Pit Droids:**

The game **REQUIRES** these patches that Lutris cannot apply automatically (at least not in the Flatpak version).*¹

**1. 16-bit SecuROM patch** - .xdelta patch for playing without CD check (that is not compatible with modern version of Windows/Wine prefixes); requires xdelta and cannot be applied automatically in Flatpak version of Lutris.

**2. QuickTime 'Safe Mode (GDI Only)' tweak** - for old Cinepak videos to play; couldn't find a way to automate this in the installer script.

        
Having said that, to allow the game to work properly, follow these steps:

**1. 16-bit SecuROM patch**

  1.1   Download/Install xdelta

    You can use your package manager (e.g., 'sudo apt install xdelta3')
  
  Helpful guide: https://command-not-found.com/xdelta3

  1.2   Download the following .xdelta patch file from this repo

    pitdroids_NOCD.xdelta - for global game version

  1.3   Locate the game folder with the original game .exe file (Pit Droids.exe)
  
    It's in your game's Wine prefix: {{ game.prefix }}/drive_c/Droids/Pit Droids.exe

  Example:
  
    /home/youruser/Games/star-wars-pit-droids/drive_c/Droids/Pit Droids.exe

  1.4   Move the .xdelta patch file into the game folder

  Example:
  
    /home/youruser/Games/star-wars-pit-droids/drive_c/Droids/pitdroids_NOCD.xdelta

  1.5   Open a Terminal from the game folder and run the patching command
  
    xdelta3 -f -d -s [game.exe] [patch_file.xdelta] [game.exe]

  Example:
  
    xdelta3 -f -d -s "Pit Droids.exe" pitdroids_NOCD.xdelta "Pit Droids.exe"

After that, the game should be patched for compatibility with modern Windows!


**2. QuickTime 'Safe Mode (GDI Only)' tweak**

  2.1   Select Star Wars: Pit Droids in your Lutris Games library, then click on the Wine button and choose 'Wine Control Panel'.

  2.2   Double-click on 'QuickTime' to open the QuickTime control panel.

  2.3   Go to Video/Advanced Settings and select 'Safe Mode (GDI Only)'.
  

**TIPS & TRICKS / KNOWN ISSUES & SOLUTIONS**

If you experience distorted sounds or visual stutter, you can try installing a newer version of QuickTime using winetricks or an external installer (https://www.pcgamingwiki.com/wiki/Star_Wars:_Pit_Droids#Videos_play_with_distorted_sound_and_visual_stutter)

**NOTE:** install.iss is an InstallShield setup component that allows to silently install the game in the background to a default directory.
I followed this guide to generate mine: https://help.kaseya.com/webhelp/en-us/5020000/index.htm?toc.htm?685.htm
It is technically not required, and you may install your game with a custom one or without it at all if you wish.
If you do decide to deviate, be mindful that the default game paths need to be adjusted accordingly in your Lutris settings!


**FOOT NOTES**

¹The game MAY run and play without a patch, but that would at least require additional tweaking for the 16-bit SafeDisc DRM for compatibility with modern versions of Windows (https://www.pcgamingwiki.com/wiki/Star_Wars:_Pit_Droids#cite_note-3) which is way outside the scope of my knowledge. Even if you could get that to work, the game would still prompt you to insert your game CD before it plays, and stop you from playing whenever you eject the CD, which can get annoying if you don't want to keep the disc spinning in your physical drive or mounted virtually all the time.
