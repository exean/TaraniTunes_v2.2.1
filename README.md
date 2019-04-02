TaraniTunes v2.2.X
===========
*Awesome music player for FrSky radios.*  
*This is modified version of TaraniTunes by [jrwieland](https://github.com/jrwieland) which is based on the Original TaraniTunes developed by [GilDev](https://github.com/GilDev). All credit goes to them.
The changes mostly focus on the UI on qx7 radios.
As this version only supports qx7 radios, please refer to jrwielands project if you own a 9xd (or don't like the ui of this build).*

### Installation

1. On your computer:
	1. Edit `itunes.lua` to have the paths to your playlist files in the playlists-array.

	2. Create a folder "lists" under /SOUNDS

	3. Create separate folders under "lists" for each desired playlist on your SD card. The folder names should pertain to the music played. **Do not add spaces to the directory names**
Examples >> `/SOUNDS/lists/3dflying`, `/SOUNDS/lists/practice`, `/SOUNDS/lists/hardrock`, `/SOUNDS/lists/competition`

	1. Create a "playlist.lua" file in each of those directories:
		title="My Playlist"
		cover="/SOUNDS/lists/practice/cover.bmp"
		playlist={
		{"Artist - Songname","SONG_FILENAME",duration}
		}
		1. cover.bmp is a 1-bit Bitmap, size 32x32 pixel, colors inverted. It is displayed during playlist selection.
		2. `Song name` is the full name to be displayed on screen
		3. `SONG_FILENAME` is the name of the song file on the sdcard (without file extension), must be 6 characters or less.
		4. `duration` is your song’s duration in seconds. 

3. Put your corresponding songs `SONG_FILENAME.wav` in `/SOUNDS/en` if your radio is in English (otherwise replace `en` with your language). They must be converted to mono, preferably normalized, and encoded in Microsoft WAV 16-bits signed PCM at a 32 kHz sampling rate, you can use [Audacity](http://www.audacityteam.org) to do that, it works great. Remember the filename must be 6 characters or less or else it will not play.

4. On your Taranis or (in companion) **This is how I setup my radio:
	1. Set “TIMER3” as follows:      
	![Timer settings](Screenshots/timer.PNG)  
	2. Set active “FLIGHT MODES” model rudder trims as follows:     
	![Flight modes settings](Screenshots/trims.PNG)  
	In fact, put every rudder trim to “`--`” for every flight mode you use.  
	3. Set “LOGICAL SWITCHES” settings as follows:  
	![Logical Switch Settings](Screenshots/LogicalSwitch.PNG)  
	**L60 will be automatically installed there is no need to enter these values**
	4. Under Telemetry “DISPLAY” Choose to display `Script iTunes`  
	![Display settings](Screenshots/DisplaySettings.PNG)

There you go! Next section will explain how to use TaraniTunes.

### Usage

From the main screen, hold “Page” to access TaraniTunes.
1. Use the rotary encoder (QX7) to sweep through the songs.
2. Press “Enter” to choose a song to play.
3. Put the “SB” switch in the middle position to start playing.
4. Put the "SB" switch in the down position to pause the song. It will continue from where it left off when the switch is returned to the middle "play" position.
5. Put “SB” in the up position to select a random song from your playlist. It will play when the switch is placed in the middle "play" position.
6. Press rudder trim right or rudder trim left to play next or previous song respectively.
7. When the song ends, the next song will automatically play and “Timer3” will be reset.
8. “Timer3” will also automatically reset if you change songs.
9.  The screen does not have to be displayed for it to work.  You can have the music playing and use the telemetry screen of your choice.  If you move the "`SB`" switch or trims the music will respond accordingly.  The only function that will not work on a different screen is selecting a new playlist (described below).

#### Changing Playlists

1. To change playlists press “MENU”.
2. A “Change Playlist Screen” will appear:  
![Change Playlist](Screenshots/ChangeList.PNG)     
3. Use the rotary encoder (QX7) to sweep through the songs.
4. Press “ENTER”, your new playlist is loaded and begins playing.

Enjoy it as much as I do.

####  Housekeeping Notes  
If you make changes to your playlist.lua files .... delete the compiled file "`playlist.lauc`" The program will always read the compiled file despite any changes you make to the source file.   By deleting the compiled file, it will automatically compile a new file from the source file.  
The same goes for any changes to the itunes.lua file.

NOTE: This only applies if you have a firmware with Lua-Compiler installed. If you do not have a lua compiler installed (or are not sure and the script does not work), add ".lua" to the playlist-filepaths in "iTunes.lua".
