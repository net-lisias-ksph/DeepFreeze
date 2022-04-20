# Deep Freeze :: Change Log

* 2015-0608: 0.15.0.5 (JPLRepo) for KSP 1.0.x
	+ First Release DeepFreeze Continued...
	+ See the Forum for full details. - Too many changes.
* 2015-0524: 0.14.3 (JPLRepo) for KSP 1.0.x PRE-RELEASE
	+ So Many fixes... and tweaks.
		- Crew are now not assigned DEAD status when frozen, but are changed from type=crew to type=unowned.
	+ Changed the Freezer Part to have Placeholder Internals and Crewspace for 10 crew by default.
	+ Removed how the mod changed the Crewspace dynamically as this was causing problems with other mods.
	+ Added Blizzy Toolbar Support and Applauncher Icons - with built in GUI that will:
	+ Display frozen crew and buttons to thaw them.
	+ Display crew in the freezer part and buttons to freeze them.
	+ Now has a Config.cfg file in the Plugins directory.
	+ Settings for DFWindowPosX and Y (default X & Y position for the GUI window).
	+ useAppLauncher = True - will use the stock app launcher buttons for the GUI window.
	+ useAppLauncher = False - will use Blizzy Toolbar (have to install this separately for the GUI window.
	+ debugging = False/True - turn on/off debug messages in the KSP log.
	+ ECreqdForFreezer = False/True - Turns on the consumption of ElectricCharge when you have frozen kerbals in the freezer part. Default this is set to False. If Set to True, you can change the amount of ElectricCharge used in the part.cfg file for the CryoFreezer. Set FrznChargeRequired = X, where X is the amount of EC to use per frozen kerbal per minute. WARNING: If you turn this feature on and you run out of electric charge Frozen Kerbals WILL DIE! randomly.
	+ Added KSP-AVC support for my forked copy of this mod.
* 2015-0521: 0.14.2 (JPLRepo) for KSP 1.0.x PRE-RELEASE
	+ Fixed Part Right-Click GUI actions glitch.
	+ Tested freezing/thawing/Swtiching Kerbals around, EVAing, borading. Switching Vessels, Recovering Vessels - Far as I can tell no other bugs and fully working now in KSP 1.0.x
* 2015-0520: 0.14.1 (JPLRepo) for KSP 1.0.x PRE-RELEASE
	+ This is a WIP pre-release fixes for KSP 1.0.x
	+ KNOWN BUGS: Part Right click menu is glitchy showing Thaw and Freeze buttons. BUT they work. When they glitch or you click one, right click/close the part menu and then right click it again to update.
	+ I need more time to fix this, but have run out of time today.
	+ FIXED: Node attach points FIXED for KSP 1.0.x strict rules.
	+ Compiled against .NET 3.5 Framework
	+ UNKNOWN BUGS: Probably many. Have done minimum testing.
* 2014-1119: 0.14 (ScottPaladin) for KSP 0.25
	+ Changelog:
		- Fixed freezing failing to abort when EC is depleted
		- Added part.cfg values for ChargeRate and ChargeRequired to allow for future parts using different EC values.
		- THIS IS A SAVEGAME BREAKING RELEASE
	+ Please see [forum thread](http://forum.kerbalspaceprogram.com/threads/92806-WIP-25-PaladinLabs-Dev-Thread-DeepFreeze-cryonic-crew-storage-v-14?p=1550330&viewfull=1#post1550330) for instructions if you want to fix a launched part.
* 2014-1112: 0.13.1 (ScottPaladin) for KSP 0.25
	+ To fix the KSP-AVC support that I screwed up the first time.
* 2014-1019: 0.012 (ScottPaladin) for KSP 0.25
	+ For real this time, I think
