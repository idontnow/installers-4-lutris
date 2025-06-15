      **** "------------------------------------------------------------------------"
      **** "Manual Patching Required for Sanity: Aiken's Artifact to play without CD"
      **** "------------------------------------------------------------------------"
      
      ****  The game requires a patch that Lutris cannot apply automatically (at least not in the Flatpak version).
      ****  If you wish to play without the game CD, follow these steps:

      ****  1. Download xdelta3:
               Install via your package manager (e.g., 'sudo apt install xdelta3')
               Helpful guide: https://command-not-found.com/xdelta3

      ****  2. Download the Patch File (sanity_fix.xdelta):"
               It can be found on this repo: https://github.com/idontnow/installers-4-lutris/blob/main/sanity-aikens-artifact/sanity_fix.xdelta

      ****  3. Locate the Original Game File (sanity.exe/Sanity.exe):
               It's in your game's Wine prefix: {{ game.prefix }}/drive_c/Games/Sanity/lithtech/sanity.exe

      ****     Example (your actual paths will be different but similar to this format):
               /home/youruser/Games/sanity-aikens-artifact/drive_c/Games/Sanity/lithtech/sanity.exe

      ****  4. Open a Terminal/Command Prompt.
               Navigate to where you saved xdelta3, or ensure xdelta3 is in your system's PATH.

      ****  5. Run the Patch Command:
               [Replace PATH_TO_ORIGINAL_SANITY.EXE and PATH_TO_SANITY_FIX.XDELTA with the full paths you copied]
               xdelta3 -f -d -s \"PATH_TO_ORIGINAL_SANITY.EXE\" \"PATH_TO_SANITY_FIX.XDELTA\" \"PATH_TO_ORIGINAL_SANITY.EXE\"

      ****     Example (your actual paths will be different but similar to this format):
               xdelta3 -f -d -s \"/home/youruser/Games/sanity-aikens-artifact/drive_c/Games/Sanity/lithtech/sanity.exe\" \"/home/youruser/Downloads/sanity_fix.xdelta\" \"/home/youruser/Games/sanity-aikens-artifact/drive_c/Games/Sanity/lithtech/sanity.exe\"

      ****  After patching, the game should be ready to play without a CD inserted/mounted!
