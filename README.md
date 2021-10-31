# SkyrimModdingLinux
Tracking how to do modding in Skyrim from Steam and Vortex (Combination of Lutris and Wine).


Totally a work in progresss. Not intended for consumption.....yet. Barely considered thoughts/notes. Will be expanded upon and formalized


1. Download game via steam. (SteamPlay - No startup commands / Proton-6.19-GE-2 (GloriousEgg))
2. Run game once to get initial splash screen where determines graphics settings. Fails miserably, defaults to low.
3. Go into options and change to ultra. Start game to get to main title screen. Then quit
4. Copy Game data folder steamapps/Skyrim Special Edition to backup folder on another drive (My warm blanket)

Open Lutris search for Vortex Mod Manager.
Follow instructions.
Get to the part in the instructions where it asks to turn off internet. Do so and click box to continue.
Lutris Dies when starting Vortex intially.

Open command prompt, cd to folder where .exe lives for Vortex   Program Files/Black..Yada/Vortex
  WINEPREFIX=/too/long wine Vortex.exe
  
Vortex starts.
Click Settings -> Vortex tab -> No Automatic Updates.
Close Vortex.

Turn interwebz back on

WINEPREFIX=/too/long winetricks
change compatibility to Win10 (Why people try and script WinXP. #StuckInPast)

Check Symlinks inside folder structure. Correctly mounts to game folder. Documents folder has game INIs. Local Settings/Application Data/Skyrim has mod list txt file.

Start Vortex again (Had to re-log to get it to restart? File process hanging in background preventing it from stopping. <---future research.)
Choose Games -> Find Skyrim -> manually choose path where symlink navigates to game folder.
Settings:
  Interface -> Automation -> ensure Deploy Mods when enabled. (My Preference)
  Vortex -> Multi-User Mode -> Per-User
  Mods -> Mod Staging Folder (no change) / Deployment Method -> Hardlink Deployment (No change)
  Nothing else in settings changes. Don't need to write it all down..
  

Download SKSE64 latest. Drag from folder (Nautilus) -> Vortex Drop File area (NEEDS TO BE INSTALLED VIA VORTEX)
---I hate this. But the things I do for modding......
Once installed, also extract a copy to another folder in your Downloads folder. Rename to SkyrimLauncher.exe
Go into game folder and rename to add suffix .old. Copy file from downloads folder to the game folder.
  Steam can now be used to launch.
  
Use Downloads folder as place to get all your mods downloaded manually from Nexus/LL (Don't judge me foo). Click and drag over.
Get all comfy with your build prior to running the first time.    If using stuff you haven't in the past, Get stuff you know works on there first before going ham on the rest.


Once you have a would be normal working build going. Fire up the game. DO NOT START A NEW GAME YET.
Go into Mods on the main screen and wait for it to do its little login thing.
Choose "T" for load order
Enable all games and escape back to the main screen.


Alt+tab out to file explorer.
Go into steamapps/common/Skyrim Special Edition/compatdata/.../Local Settings/Application Data/Skyrim/Plugins.txt


Select all and Copy. Open text editor to a new file and save this someplace with the same name. This is Charlie's Golden ticket. No loosey the goosey.
Can close game down.

Go ham in Vortex.
After done installing mods. Goto plugins tab. Sort by load order
Open the golden ticket and start using this format to enter in ALL THE PLUGIN NAMES. For safety sake I went in order top down assuming this was also the load order.

Do this process save, select all. Go back to the original file. Select All paste -> Save.
Open Game -> go back to mods, ensure all is checked and in the order you have in the file. If not find where the typo is and go back and fix it. Repeat this process until FULLY WORKING.  Save the golden ticket in three other places, probably in a safety deposit box as well.

Create new game to play. Should take less than an hour for 90% of it.  Took me 1.5 on a practiced run. because I am a slow typer when I have fear instilled in me. (CRIES).
