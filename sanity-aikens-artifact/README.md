You can add **Sanity: Aiken's Artifact** to your Lutris library on Lutris.net:
https://lutris.net/games/sanity-aikens-artifact/

**The Lutris installer file can be found on this repo for your own customization.**

**NOTE:** install.iss is an InstallShield setup component that allows to silently install the game in the background to a default directory.
I followed this guide to generate mine: https://help.kaseya.com/webhelp/en-us/5020000/index.htm?toc.htm?685.htm
It is technically not required, and you may install your game with a custom one or without it at all if you wish.
If you do decide to deviate, be mindful that the default game paths need to be adjusted accordingly in your Lutris settings!
      
**Manual Patching Required for Sanity: Aiken's Artifact to play without CD**
      
The game needs a patch that Lutris cannot apply automatically (at least not in the Flatpak version). The game can run without a patch successfully, but it will prompt you to insert your game CD before it plays, which can get annoying if you don't want to keep the disc spinning in your physical drive or mounted virtually.
            
If you wish to play without the game CD, follow these steps:

1. Install xdelta3:
   Use your package manager (e.g., 'sudo apt install xdelta3')
               
   Helpful guide: https://command-not-found.com/xdelta3

2. Download an extract the patched client.dll and cshell.dll files (created by user CyberDemon@) from here:
      
   https://www.old-games.ru/game/download/get.php?fileid=27696&modal=1
      
3. Download the .xdelta patch file for the version of the game you have from this repo:
      
        a)  SanityUS_NOCD.xdelta - for "Sanity Aiken's Artifact" (US version)
        b)  SanityEU_NOCD.xdelta - for "Aiken's Artifact" (EU/UK version)*

4. Locate the original game .exe file (sanity.exe/Sanity.exe):
   It's in your game's Wine prefix: {{ game.prefix }}/drive_c/Games/Sanity/lithtech/sanity.exe OR {{ game.prefix }}/drive_c/Games/Sanity/LITHTECH/Sanity.exe

   Example:

        /home/youruser/Games/sanity-aikens-artifact/drive_c/Games/Sanity/lithtech/sanity.exe

   NOTE:  I suggest to make a backup of your original sanity.exe file (and client.dll), just in case.
      
5. Copy:

        the patched client.dll and cshell.dll files (from step 2);
        +
        SanityUS_NOCD.xdelta OR SanityEU_NOCD.xdelta (from step 3, depending on the version you have);

   To:

        The /lithtech/ folder where the sanity.exe is located.

   Overwrite the original client.dll file.

6. Open a Terminal/Command Prompt from your /lithtech/ folder and run the xdelta3 patch command:

        xdelta3 -f -d -s [game.exe] [patch_file.xdelta] [game.exe]

   Example:

        xdelta3 -f -d -s sanity.exe SanityUS_NOCD.xdelta sanity.exe

After patching, the game should be ready to play without a CD inserted/mounted!

**TIPS & TRICKS & KNOWN ISSUES & SOLUTIONS**

Be sure to set your preferred resolution under **Display** in the game launcher!
Select your graphics card under **Displays** to see more options under **Resolutions** (may need to click multiple times).

If you can't select your display resolution from the launcher after applying the patch, try changing your resolution through the in-game **Display** settings.
Alternatively, go to the */lithtech/ folder and manually edit the **autoexec.cfg** settings file:
      
        "screenwidth" "XXXX"
        "screenheight" "YYYY"
      
If you experience audio issues (choppy voice overs and sound while music plays fine), you can try the following:
Open **winecfg**/**Wine Configuration** for your game, go to the **Libraries** tab and set **dsound** to **Builtin**.
      
If you have no music in the main menu/cutscenes, check if **directmusic** and **dmusic** are installed via **winetricks**.

An optional FoV fix is available (for resolutions wider than 16:9 aspect ratio) here: https://community.pcgamingwiki.com/files/file/2862-sanity-aikens-artifact-fov-fix/
