# SkyrimModdingLinux
Tracking how to do modding in Skyrim from Steam and Vortex (Combination of Lutris and Wine).


Totally a work in progresss. Not intended for consumption.....yet. Barely considered thoughts/notes. Will be expanded upon and formalized


1. Download game via steam. (SteamPlay - No startup commands / Proton-6.19-GE-2 (GloriousEgg))
2. Run game once to get initial splash screen where determines graphics settings. Fails miserably, defaults to low.
3. Go into options and change to ultra. Start game to get to main title screen. Then quit (Just for INI creation INIways.....cough)
4. Copy Game data folder steamapps/Skyrim Special Edition to backup folder on another drive (My warm blanket)
5. Navigate to steamapps folder, edit appmanifest_489830.acf permissions to read-only. (Anniversary Ed. can gtfo.....for now.)

Open Lutris search for Vortex Mod Manager.
Follow instructions.
Get to the part in the instructions where it asks to turn off internet. Do so and click box to continue.
Lutris Dies when starting Vortex intially. After 20 mins of staring at a non-moving terminal ctl+c to kill process.

Open command prompt, cd to folder where .exe lives for Vortex   Program Files/Black..Yada/Vortex
  WINEPREFIX=/too/long wine Vortex.exe
  
Vortex starts. (But sloooooooooooooow) Took 5 minutes to switch a tab. Ain't nobody got time for dat.....except me.
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

My Normal First build mods:
- SKSE
- SKSE64 INI Pre Download (yes, yes I am lazy :P )
- XP32 Maximum Skeleton Special Extended
- XP32 Maximum Skeleton Special Extended Fixed Scripts
- Unofficial Skyrim Special Edition Patch
- UI Extensions
- SRT Crash Fix SSE
- Papyrus Extender SSE
- Address Library for SKSE Plugins
- JContainer
- FNIS Behavior SE
- FileAccess Interface for Skyrim SE Scripts - FISSES
- Auto Input Switch
- Fuz Ro D'oh
- Alternate Start - Live another life


Once you have a would be normal working build going. Fire up the game. DO NOT START A NEW GAME YET.
Go into Mods on the main screen and wait for it to do its little login thing.
Choose "T" for load order
Enable all mods and escape back to the main screen.


Alt+tab out to file explorer.
Go into steamapps/common/Skyrim Special Edition/compatdata/.../Local Settings/Application Data/Skyrim/Plugins.txt


Select all and Copy. Open text editor to a new file and save this someplace with the same name. This is Charlie's Golden ticket. No loosey the goosey.
Can close game down.

Go ham in Vortex.
After done installing mods. Goto plugins tab. Sort by load order
Open the golden ticket and start using this format to enter in ALL THE PLUGIN NAMES. For safety sake I went in order top down assuming this was also the load order.

Do this process repeatedly:   save, select all. Go back to the original file. Select All paste -> Save.
Open Game -> go back to mods, ensure all is checked and in the order you have in the file. If not find where the typo is and go back and fix it. Repeat this process until ALL Mods are listed in order.  Save the golden ticket in three other places, probably in a safety deposit box as well. Add to it, and back it up.

Create new game to play. Should take less than an hour for 90% of it.  Took me 1.5 on a practiced run. because I am a slow typer when I have fear instilled in me. (CRIES).

Vortex Notes:
FNIS Integration -> Yes (on Dashboard) (Like having snapshots of FNIS as mods get installed, At the end before actual game run, run FNIS manually --next line)
Where the background pic is for Skyrim, can use that to manually run FNIS, and BodySlide
GAME CANNOT AND SHOULD NOT BE RUN FROM VORTEX. NEEDS TO BE RUN VIA STEAM.

Will try and get SSEEDIT and Wyre Bash running from Vortex (TODO)
