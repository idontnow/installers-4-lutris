You can add the old Blair Witch Volume trilogy of games to your Lutris library on Lutris.net:

Volume I - https://lutris.net/games/blair-witch-volume-i-rustin-parr/
Volume II - https://lutris.net/games/blair-witch-volume-ii-the-legend-of-coffin-rock/
Volume III - https://lutris.net/games/blair-witch-volume-iii-the-elly-kedward-tale/

The Lutris installer files can be found on this repo for your own customization.

NOTE: install.iss is an InstallShield setup component that allows to silently install the game in the background to a default directory. I followed this guide to generate mine: https://help.kaseya.com/webhelp/en-us/5020000/index.htm?toc.htm?685.htm It is technically not required, and you may install your game with a custom one or without it at all if you wish. If you do decide to deviate, be mindful that the default game paths need to be adjusted accordingly in your Lutris settings!

TIPS & TRICKS & KNOWN ISSUES & SOLUTIONS

   *For stability, restrict the game to 1 CPU core and set 30-60 FPS limit (higher FPS = more glitches).
   
   *Use dgVoodoo for higher resolutions than 640x480.
   
   *Install "winetricks icodecs" in the game prefix to play videos (not included in the installer for Lutris Flatpak version compatibility). If all else fails for Lutris Flatpak - you can install icodecs using your system winetricks by specifying the wineprefix folder; then set Lutris to use that.
    
