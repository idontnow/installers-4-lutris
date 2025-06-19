You can add **Star Wars: Pit Droids** to your Lutris library on Lutris.net:

https://lutris.net/games/star-wars-pit-droids/

**The Lutris installer file can be found on this repo for your own customization.**


**NOTE:** To allow the game access to DirectX and QuickTime runtime files, my script requires:
1. Using a 32-bit wineprefix
2. Using Winetricks to set Windows version to Windows 98
  
I couldn't think of a workaround for Windows XP and above with a 64-bit wineprefix for now, but the script will need to be updated for compatibility once 32-bit wineprefixes will be deprecated.

It appears that the issue with 64-bit wineprefixes is that they install runtimes into the SysWow64 folder and not System32, which is why the game pops up a window "The game requires DirectX 6.1" when you try to play it in a 64-bit Wine prefix. (https://github.com/lutris/lutris/issues/1850)


**Manual Patching REQUIRED for Star Wars: Pit Droids:**

**1. 16-bit SecuROM patch** - .xdelta patch for playing without CD checks; cannot be applied automatically in Flatpak version of Lutris
**2. QuickTime 'Safe Mode (GDI Only)' tweak** - for old Cinepak videos to play; couldn't find a way to automate this in the installer script
  
The game **REQUIRES** these patches that Lutris cannot apply automatically (at least not in the Flatpak version).*¹
        
Having said that, if you wish to play without the game CD and with videos working properly, follow these steps:

**1. 16-bit SecuROM patch**

  1.1   Install xdelta3

    Use your package manager (e.g., 'sudo apt install xdelta3')
  
  Helpful guide: https://command-not-found.com/xdelta3

  1.2   Download the following .xdelta patch file from this repo

    pitdroids_NOCD.xdelta - for global game version

  1.3   Locate the original game .exe file (Pit Droids.exe)
  
    It's in your game's Wine prefix: {{ game.prefix }}/drive_c/Program Files/Lucas Learning/Star Wars Pit Droids/Pit Droids.exe

  Example:
  
    /home/youruser/Games/sanity-aikens-artifact/drive_c/Program Files/Lucas Learning/Star Wars Pit Droids/Pit Droids.exe

  1.4   Open a Terminal/Command Prompt from your /Star Wars Pit Droids/ folder and run the xdelta3 patch command
  
    xdelta3 -f -d -s [game.exe] [patch_file.xdelta] [game.exe]

  Example:
  
    xdelta3 -f -d -s "Pit Droids.exe" pitdroids_NOCD.xdelta "Pit Droids.exe"

After that, the game should be ready to play without a CD inserted/mounted!


**2. QuickTime 'Safe Mode (GDI Only)' tweak**

  2.1   Select Star Wars: Pit Droids in your Lutris Games library, then click on the Wine button and choose 'Wine Control Panel'.

  2.2   Double-click on 'QuickTime' to open the QuickTime control panel.

  2.3   Go to Video Settings and select 'Safe Mode (GDI Only)'.
  

**TIPS & TRICKS / KNOWN ISSUES & SOLUTIONS**

If you experience distorted sounds or visual stutter, you can try installing a newer version of QuickTime using winetricks or an external installer (https://www.pcgamingwiki.com/wiki/Star_Wars:_Pit_Droids#Videos_play_with_distorted_sound_and_visual_stutter)

**NOTE:** install.iss is an InstallShield setup component that allows to silently install the game in the background to a default directory.
I followed this guide to generate mine: https://help.kaseya.com/webhelp/en-us/5020000/index.htm?toc.htm?685.htm
It is technically not required, and you may install your game with a custom one or without it at all if you wish.
If you do decide to deviate, be mindful that the default game paths need to be adjusted accordingly in your Lutris settings!


**FOOT NOTES**

¹The game MAY run and play without a patch, but that would at least require additional tweaking for the 16-bit SafeDisc DRM (https://www.pcgamingwiki.com/wiki/Star_Wars:_Pit_Droids#cite_note-3) which is way outside the scope of my knowledge. Even if you can get that to work, the game will still prompt you to insert your game CD before it plays, and stop you from playing if you eject the CD, which can get annoying if you don't want to keep the disc spinning in your physical drive or mounted virtually.
