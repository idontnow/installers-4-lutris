You can add **Star Wars: Pit Droids** to your Lutris library on Lutris.net and install it from there:
https://lutris.net/games/star-wars-pit-droids/

Alternatively, manually launch the installer .yml found in this repo from within Lutris itself.

**The Lutris installer file can be found on this repo or via Lutris once made public.**

**NOTE:** install.iss is an InstallShield setup component that allows to silently install the game in the background to a default directory.
I followed this guide to generate mine: https://help.kaseya.com/webhelp/en-us/5020000/index.htm?toc.htm?685.htm
It is technically not required, and you may install your game with a custom one or without it at all if you wish. If you do decide to deviate, be mindful that the default game paths need to be adjusted accordingly in your Lutris settings!
  
**Manual Patching Required for Star Wars: Pit Droids to play without CD**
  
The game needs a patch that Lutris cannot apply automatically (at least not in the Flatpak version). The game can run without a patch successfully, but it will prompt you to insert your game CD before it plays, which can get annoying if you don't keep the disc spinning in your physical drive or mounted virtually.
        
If you wish to play without the game CD, follow these steps:

1. Install xdelta3:
   Use your package manager (e.g., 'sudo apt install xdelta3')

   Helpful guide: https://command-not-found.com/xdelta3

2. Download the .xdelta patch file from this repo:

        pitdroids_NOCD.xdelta - for global game version

3. Locate the original game .exe file (Pit Droids.exe):
   It's in your game's Wine prefix: {{ game.prefix }}/drive_c/Program Files/Lucas Learning/Star Wars Pit Droids/Pit Droids.exe

  Example:
  
        /home/youruser/Games/sanity-aikens-artifact/drive_c/Program Files/Lucas Learning/Star Wars Pit Droids/Pit Droids.exe

4. Open a Terminal/Command Prompt from your /Star Wars Pit Droids/ folder and run the xdelta3 patch command:
  
        xdelta3 -f -d -s [game.exe] [patch_file.xdelta] [game.exe]

  Example:
  
        xdelta3 -f -d -s "Pit Droids.exe" pitdroids_NOCD.xdelta "Pit Droids.exe"

After patching, the game should be ready to play without a CD inserted/mounted!

**TIPS & TRICKS & KNOWN ISSUES & SOLUTIONS**

If you experience distorted sounds or visual stutter, you can try installing a newer version of QuickTime using winetricks or an external installer (https://www.pcgamingwiki.com/wiki/Star_Wars:_Pit_Droids#Videos_play_with_distorted_sound_and_visual_stutter)
