You can add **The Typing of the Dead** to your Lutris library on Lutris.net:
https://lutris.net/games/the-typing-of-the-dead/

**The Lutris installer file can be found on this repo for your own customization.**

**Manual Patching Required for Sanity: Aiken's Artifact to play without CD**
      
The game needs a patch that Lutris cannot apply automatically (at least not in the Flatpak version). The game can run without a patch successfully, but it will prompt you to insert your game CD before it plays, which can get annoying if you don't want to keep the disc spinning in your physical drive or mounted virtually.
            
That said, if you wish to play without the game CD, follow these steps:

1. Download/Install xdelta

         Use your package manager (e.g., 'sudo apt install xdelta3')
               
   Helpful guide: https://command-not-found.com/xdelta3

2. Download the .xdelta patch file from this repo for the version of the game you have
      
        a)  Todus_US.xdelta - for US version
        b)  Tod_e_EU.xdelta - for EU/UK version
        c)  Tod_JP.xdelta - for JP version

3. Locate the folder containing the original game .exe file (Todus.exe, Tod_e.exe or Tod.exe)

   It's in your game's Wine prefix:

         {{ game.prefix }}/drive_c/Games/TToTD/

   Example:

        /home/youruser/Games/the-typing-of-the-dead/drive_c/Games/TToTD/Todus.exe
      
4. Copy the patch files to the folder containing the game's launcher .exe file

         e.g. /home/youruser/Games/the-typing-of-the-dead/drive_c/Games/TToTD/
   
         ADD "Todus_US.xdelta" (or "Tod_e_EU.xdelta", or "Tod_JP.xdelta")

5. Open a Terminal/Command Prompt from your /TToTD/ folder and run the xdelta patch command:

        xdelta3 -f -d -s [game.exe] [patch_file.xdelta] [game.exe]

   Example:

        xdelta3 -f -d -s Todus.exe Todus_US.xdelta Todus.exe

After patching, the game should be ready to play without a CD inserted/mounted!


**TIPS & TRICKS / KNOWN ISSUES & SOLUTIONS**

Stage 3's cutscene has a very loud speedboat sound effect that drowns out the dialogue (and can be painful to listen to, depending on your audio setup). A modified boat_fast2.wav with the volume lowered can be downloaded here. Replace the file in \sound\SE\STAGE3_SE. (https://www.pcgamingwiki.com/wiki/The_Typing_of_the_Dead#Loud_cutscene_sound_effect)

**NOTE:** install.iss is an InstallShield setup component that allows to silently install the game in the background to a default directory.
I followed this guide to generate mine: https://docs.revenera.com/installshield24helplib/helplibrary/CreatetheResponseFile.htm
It is technically not required, and you may install your game with a custom one or without it at all if you wish.
If you do decide to deviate, be mindful that the default game paths need to be adjusted accordingly in your Lutris settings!
