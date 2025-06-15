      **** "-----------------------------------------------------------------------------------"
      **** "The Lutris installer file can be found on this repo or via Lutris once made public."
      **** "-----------------------------------------------------------------------------------"

           NOTE: record.iss is an InstallShield setup component that allows to silently install the game in the background to C:/Games/Sanity by default (a recommended directory for the game without spaces or an excessive amount of characters in the path).
           I followed this guide to generate mine: https://help.kaseya.com/webhelp/en-us/5020000/index.htm?toc.htm?685.htm
           It is technically not required, and you may install your game with a custom one or without it at all if you wish.
           If you do decide to deviate, be mindful that the default game paths need to be adjusted accordingly in your settings!
      
      **** "------------------------------------------------------------------------"
      **** "Manual Patching Required for Sanity: Aiken's Artifact to play without CD"
      **** "------------------------------------------------------------------------"
      
      ****  The game needs a patch that Lutris cannot apply automatically (at least not in the Flatpak version).
      ****  The game can run without the patch successfully, but it will prompt you to insert your game CD before it plays.
            
      ****  If you wish to play without the game CD, follow these steps:

      ****  1. Install xdelta3:
               Use your package manager (e.g., 'sudo apt install xdelta3')
               
               Helpful guide: https://command-not-found.com/xdelta3

      ****  2. Download the .xdelta patch file for the version of the game you have from this repo:
      
            a)  SanityUS_NOCD.xdelta - for "Sanity Aiken's Artifact" (US version)
            b)  SanityEU_NOCD.xdelta - for "Aiken's Artifact" (EU/UK version)

      ****  3. Locate the original game .exe file (sanity.exe/Sanity.exe):
               It's in your game's Wine prefix: {{ game.prefix }}/drive_c/Games/Sanity/lithtech/sanity.exe OR {{ game.prefix }}/drive_c/Games/Sanity/LITHTECH/Sanity.exe

      ****     Example:
               /home/youruser/Games/sanity-aikens-artifact/drive_c/Games/Sanity/lithtech/sanity.exe

               Copy the patch file to the /lithtech/ folder where the sanity.exe is located.
               
               NOTE: I suggest to make a backup of your original sanity.exe file, just in case.

      ****  4. Open a Terminal/Command Prompt and run the Patch Command:

               xdelta3 -f -d -s [game.exe] [patch_file.xdelta] [game.exe]

      ****     Example:
               xdelta3 -f -d -s sanity.exe SanityUS_NOCD.xdelta sanity.exe

      ****  After patching, the game should be ready to play without a CD inserted/mounted!
