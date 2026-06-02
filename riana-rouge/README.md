You can add **Riana Rouge** to your Lutris library on Lutris.net:

https://lutris.net/games/riana-rouge/

**The Lutris installer file can be found on this repo for your own customization.**

- Start: Click 'Run Installed Operating System' to boot into Windows 95.
- Install: Open 'My Computer', navigate to the 'E:' drive (Disc 1), and run SETUP.EXE. Skip installing DirectX 5.
- Run Game: Open 'Riana.exe' from where the game is installed. Recommended to add a shortcut to it on your Desktop.
- Swap Discs: When prompted by the game for a disc, press Ctrl+F12 to access the DOSBox Pure UI and select the INSERT option for the required disc.
- Exit Game: If on a screen without the option to Quit, press Ctrl+F12, open the 'On-Screen Keyboard', and click 'Alt' followed by 'F4'.
- End: Be sure to Shut Down Windows 95 before closing DOSBox to avoid data corruption and ScanDisk checks!

**TIPS & TRICKS / KNOWN ISSUES & SOLUTIONS**

Using 'Dynamic' or 'Auto' DOSBox CPU Core emulation method may cause the "Windows 95 I/O protect error", which prevents Windows 95 from booting. To allow Windows 95 to boot with faster than expected/modern CPUs, go to Settings > Advanced > CPU Core > set 'Normal' or 'Simple'. (NOTE: My Lutris installer script automatically sets 'Normal' by default.)

Command.com/MS-DOS Shell freezes the system when opened in Windows 95 on DOSBox (not that you should need it). Workaround - press Ctrl+Alt+Delete twice to get BSOD, then hit Enter and close the Task Manager and you can proceed.
