Slmod- multiplayer server mod for new mission logic functionality
=========
Server adminstation and mission functionality mod for Digital Combat Simulator


Author: Speed, Grimes
DCS 2.5+ Compatibility Thread: https://forums.eagle.ru/showthread.php?t=155563


=====
Original Forum Thread: http://forums.eagle.ru/showthread.php?t=80979
Author: Speed

Documentation
====
The attached pdf "slmodvX_Y.pdf" is attached in the download for original documentation. 
Also see wiki tab on github: https://github.com/mrSkortch/DCS-SLmod/wiki 


Note that the source file for the pdf is not available, thus it will not be updated. 

=======

If you want to donate do Grimes (mrSkortch, SLmod creator), feel free to use the link below:

[![](https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_donations&business=X8CHU2343FRKA&currency_code=USD&source=url)


Installation
===

1. Download slmod via code dropdown button and downloading zip or if a release is available.
2. Navigate to active saved games folder used by DCS. Generally it will be in: C:\Users\<windowsUserName>\Saved Games\DCS.
3. Extract the scripts folder into your saved games\DCS folder. There should be:
	DCS\Scripts\Hooks\slmodGameGUI.lua
	DCS\Scripts\net\SlmodvX_Y\ with a number of lua files within. 
4. Start game. If loaded correctly slmod will create an Slmod folder in your Saved Games\DCS folder. In this folder you will find your config, chat logs, and stats.
5. Slmod is only loaded when the game starts and the game must be reloaded in order for changes to the config file to take effect. 




Description
===
Server Lua Mod, "Slmod", is a multiplayer server mod created by "Speed". Despite the uninspired name, it provides a significant set of enhancements for DCS multiplayer servers, including multiplayer server administration tools, multiplayer stats tracking, enhanced multiplayer server operation, enhanced mission scripting capabilities, and several other useful features. As it is a server mod, multiplayer clients do not need to have it installed to use it.

Slmod includes the SlmodStats system. It keeps persistent stats on multiplayer clients who join the server, tracking their kills, deaths, friendly fire incidents, flight time, etc. It can save and display player stats from their entire history on the server, or from just a single mission alone. More information can be found in the SlmodStats section of this manual.

Slmod also includes the Slmod Admin Menu. This menu allows registered server admins to remotely manage the server through chat-based menu system. Server admins can kick players, ban players, unban players, add players to the list of server admins, remove players from the list of server admins, restart the mission, load a different mission, pause/unpause the game, etc. More info about this feature can be found in the Slmod Admin Menu section of this manual.

Using the data acquired through SlmodStats, Slmod can auto-kick or auto-ban players for team hitting, team-killing, team-collision-hitting, and/or team-collision-killing. This feature is encompassed in the new SlmodAutoAdmin system, and is highly customizable. For more on this feature see the SlmodAutoAdmin section of this manual.

Slmod accomplishes enhanced mission scripting capabilities by adding several dozen new Lua functions to the “Mission Scripting” Lua environment. These new Lua functions provide capabilities to detect game world conditions that are undetectable with traditional triggers, allow increased client interaction with the game environment, and to output dynamic trigger text messages or chat messages. The function listing and how to use them can be found in the Slmod Scripting Functions Listing section of this manual.

In addition, Slmod also adds the following features:
- a help menu
- a chat logging system
-Pause or unpause the server based on whether or not clients are connected;
-A server Message of the Day (MOTD) system;
-The capability to export, in real time, alive unit information and events;
-Slmod Coordinate Conversion Utility (chat-based coordinate converter capable of converting between four different coordinate systems);

As it is named, Slmod is a server mod. It does not need to be installed by clients. It also will not function in single player. As tracks are replayed using the single player .exe, Slmod may also break track replay if any of the Slmod mission scripting functions were used to trigger in-game events. If your mission does not use any Slmod mission scripting functions (the vast majority won't, especially now that we have a very capable mission scripting environment already built in), then you don't need to worry about this.

Keep in mind that Slmod is NOT supported by Eagle Dynamics. In order to obtain many of its capabilities, Slmod must utilize some Lua functionalities not officially supported by Eagle Dynamics, or even necessarily intended for user modding in the first place. Because of this, and because Eagle Dynamics is constantly upgrading and improving the game world, Eagle Dynamics cannot be held responsible for a patch causing Slmod to no longer function correctly. That said, I will do my very best to keep Slmod functioning through future patches. Most of the code that Slmod is dependent on is not likely to undergo drastic changes in the near future, there are always such things as bugs, and sometimes relatively minor changes can have major ripple-down effects.


Contribution Guide
===
Contributions can be made with a standard github pull request model.  Code developed for the next release should be requested to be pulled into the "develop" branch.
Pull requests not targetted for "develop" will be denied.  For hotfixes please open a ticket describing the problem and ideally a fix and your changes will be attributed in the relevant commit message.  It's done like this because unfortunately github provides no tools to target to a new hotfix branch, and github tools are exclusively used in the administration of this repository and we wish to minimize the amount of unvetted code into master.
