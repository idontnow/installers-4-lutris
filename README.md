# installers-4-lutris
Custom .yml installer scripts for Lutris on Linux

<img width="1758" height="576" alt="idontnow_banner_github_v3_minorfixcrop_halfsized2" src="https://github.com/user-attachments/assets/8c1f282b-6b2a-4a4e-8492-122c093e4278" />

This project provides custom Lutris installer scripts for older PC games, with a focus on titles that are:  

* Released between 1998–2002 for Windows operating systems.
* Out of print and unavailable on modern digital storefronts.
  
These scripts are compatible with both native and Flatpak Lutris installations and have been tested exclusively with 64-bit Wine prefixes. 
  
The Goal is to make it easy to install and play vintage Windows games on modern Linux, using automation to install the game files and configure custom settings (along with simple instructions for any manual setup).   
  
## Current Installers:  
[Star Wars: Pit Droids ](https://github.com/idontnow/installers-4-lutris/tree/main/star-wars-pit-droids)  
[Sanity: Aiken’s Artifact  ](https://github.com/idontnow/installers-4-lutris/tree/main/sanity-aikens-artifact)  
[Blair Witch Volume I–III  ](https://github.com/idontnow/installers-4-lutris/tree/main/blair-witch-volume-trilogy)  
[Star Wars: DroidWorks](https://github.com/idontnow/installers-4-lutris/tree/main/star-wars-droidworks)  
  
## Planned Installers:  
[The Typing of the Dead](https://lutris.net/games/the-typing-of-the-dead/)  
[Riana Rouge](https://lutris.net/games/riana-rouge/)  
[Discworld Noir](https://lutris.net/games/discworld-noir/)  
[Dragonriders: Chronicles of Pern](https://lutris.net/games/dragonriders-chronicles-of-pern/)  
[Heavy Metal F.A.K.K.²](https://lutris.net/games/heavy-metal-fakk-2/)  
[American McGee’s Alice](https://lutris.net/games/american-mcgees-alice/)  
…and more to come.  
  
## Where to Get The Games  

* Some may still be purchased (boxed or otherwise) from resellers on online marketplaces like [eBay.com](https://www.ebay.com/) or [Eneba.com](https://www.eneba.com).  
* In case a copy you own is damaged, there are various archival websites online like [archive.org](https://archive.org/) or [MyAbandonware.com](https://www.myabandonware.com/), hosting digital copies of the original game discs.  
* Eventually, with enough interest, these seemingly abandoned games may yet appear for sale on platforms like [Steam](https://store.steampowered.com/) or [GOG](https://www.gog.com/) (make sure to vote in the [GOG Dreamlist](https://www.gog.com/dreamlist/)!)
  
## How to Use  
  
1. Install [Lutris](https://lutris.net/downloads) on your Linux distribution of choice.  
  
2. Download the .yml installer file for the game you want to install.  
  
3. In Lutris, click **+** → **Install from a local install script**.  
  
4. Select the .yml file you downloaded.  
  
5. Follow the instructions provided by the installer.  
  
That’s it — Lutris will handle the installation and custom configuration.  
If any additional steps are needed, they will be mentioned in the script description.  
  
_**NOTE:** You may need to manually click to close the occasional dialog window._
  
## Bonus Resources  
  
### 16-bit Setup Executable Replacement  
  
This repository also hosts copies of [generic 32-bit InstallShield setup executables](https://github.com/idontnow/installers-4-lutris/tree/main/generic_32bit_installer) (versions 3 and 5).  
  
These may be useful when manually installing games that shipped with 16-bit Windows setup executables, which cannot run on 64-bit Windows operating systems.  
  
In those cases, you can copy the CD contents to a drive and replace the original Setup.exe with one of the provided executables, depending on the version of the original. This will allow the setup to run on modern 64-bit Windows systems/Wine prefixes that still have limited support for 32-bit software.  
  
### SafeDisc/SecuROM CD Check Preservation  
  
I have found a project called [SafeDiscShim](https://github.com/RibShark/SafeDiscShim) by [RibShark](https://github.com/RibShark) which aims to make this outdated DRM compatible with modern systems (rather than effectively surgically disabling it). You may be interested in utilising that compatibility tool to preserve the disc check functionality of your games, as it works well with regular CDs and mounted images on modern systems.  
  
It's possible that this tool or a similar one could be utilized instead of the .xdelta patch method in this repo for a better user experience after installation (it could be an option in the installer script), but for now I prefer both to save on disk space from the size of virtual images and to preserve my old physical CDs.  
  
In any case, big respectful shout-out to [**RibShark**](https://github.com/RibShark)! 🫡  
  
## Contributing to This Project  
  
Found a bug, want to improve an existing script, or have a new one to share? Your contributions are welcome!  
  
1.  **For new scripts or improvements:** Fork this repository, make your changes, and submit a pull request.  
2.  **For bugs or suggestions:** Open a new issue with a clear description of the problem or your idea.
  
## Terms of Use  
  
By using the scripts and instructions provided in this project, you acknowledge and agree to the following:  
  
**Non-Profit Passion Project:**  
This is a non-profit, passion-driven project created for the purpose of game preservation and enthusiast sharing. It is not intended for financial gain and does not generate any revenue.  
  
**No Ownership of Third-Party Content:**  
This project, its author, and its contributors do not claim any ownership of the games or any original software used in their installation. All copyrights, trademarks, and intellectual property for the games and their components belong to their respective owners.  
The only original works in this repository are the Lutris installer scripts, their accompanying instructions, this README.md file, and any unique graphical assets, such as the banner image.  
  
**Use at Your Own Risk; No Warranty:**  
These scripts are provided "as is" without any warranty of any kind, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose, or non-infringement. The user assumes all risk and responsibility for any loss of data, hardware damage, or any other issues that may arise from the use of these scripts.  
  
**Copyright and Circumvention:**  
The purpose of this project is to provide a user-friendly way to install and play vintage software. However, if any content or instructions in this repository are found to infringe upon copyright laws or laws concerning the circumvention of technological measures that control access to copyrighted works, the author is willing to promptly remove the offending files or instructions upon official request from the copyright holder.  
  
## Addendum - An Enduring Hope  
  
_Some save the boxes, some save the bits. I save the games._  
  
To preserve video games is to preserve imagination, experimentation, and the culture of an era. While museums and archives are great for this, true preservation means keeping forgotten worlds playable at home. My installer scripts are a tribute to the art of play, ensuring these digital legacies are not just stored, but enjoyed on newer devices.  
  
The tools/instructions here which aid in the removal of compromised, obsolete copy protection and DRM software are here for the sake of helping to make legally-owned game copies playable on modern systems; not for monetary gain or any kind of malicious intent. For now, I believe the ends justify the means, at least until these out-of-print games can be re-released commercially with official patches.  
  
In the interest of keeping things somewhat kosher, my scripts require you to insert/mount an original game CD before they can proceed. They will only work with 1:1 or compatible copies of the original discs.  
  
However, just as the old software they're meant to install, these scripts will eventually become obsolete. As software and operating systems evolve, these automations may one day fail. Still, I hope the research and effort that went into them will be useful for future generations of curious players and tinkerers, saving them time and frustration.  
  
Having said that all that, I await for simpler days, when it is easy for people to legally own working copies of video games more than a quarter-century after their original release. After all, the real goal is to get back to the important parts: expanding our imaginations in these virtual worlds, having unique experiences, and sharing our favorite ones with others.  
  
If you enjoy playing any of the games mentioned here, please be sure to support the developers and their collaborators by purchasing licensed copies of their latest works! ✌️  
