# Deep Freeze :: Change Log

* 2015-0625: 0.16.0.3 (JPLRepo) for KSP 1.0.3
	+ Added the following fields to the Settings file (settings menu in space center)
	+ heatamtMonitoringFrznKerbals - this is the amount of heat in Kilowatts generated per kerbal to run the monitoring equipment. Is only relevant is xxxx is set to on.
	+ heatamtThawFreezeKerbal - this is the amount of heat in Kilowatts generated per second when thawing or freezing a kerbal. Is only relevant if xxx is set to ON.
	+ Don't forget the new heat system in KSP, the amount of kW of heat is proportionate to the part's thermal mass.
	+ Fixed Electric Charge and Heat monitoring - it was not storing the time last check was performed correctly and not calculating the EC usage and heating correctly.
	+ This WILL create an issue for anyone who has been using these features in the previous versions. You may notice the first time you switch to a freezer equiped vessel that previously had EC usage or heat generation switched on that it will instantly use up 95% of your EC. So be prepared.
	+ This change will ensure tracking of the last time checked is correct. The down-side is that due to no EC consumption or heat generation during high timewarp or when the vessel is not the active vessel that when you return to that vessel a spike in usage will occur.
	+ Future versions to address this by providing monitoring and warning of EC usage and heat generation for all vessels including inactive vessels.
	+ Added Messages in the bottom right corner of the screen when you are IVA mode displaying the current Kerbal's name and Crypod number.
	+ Pick-up new Ship Manifest Interface DLL and corrected bug if transferring crew into a freezer that is full of frozen kerbals.
	+ Fixed Pod Numbers in internal model to be correctly numbered.
* 2015-0623: 0.16.0.2 (JPLRepo) for KSP 1.0.3
	+ Support for KSP 1.0.3
	+ Enhancements to the DeepFreeze API for other mod support
	+ Modders refer to the [WIKI page](https://github.com/JPLRepo/DeepFreeze/wiki/DeepFreeze-API-documentation-%28DFInterface.DLL%29)
	+ This is NOT save game breaking if you are upgrading from V0.16.0.0
* 2015-0621: 0.16.0.0 (JPLRepo) for KSP 1.0.x
	+ IVA portrait cameras now correctly update when you thaw and xfer kerbals.
	+ Did I mention portrait cameras? Oh wait - IVA Internal texturing now completed for Large Freezer.
	+ All Praise to MerlinsMaster for his Amazing!! Internal modelling and texturing.
	+ So now the portrait cameras will correctly display thawed (Crewed?) crew and Frozen crew.
	+ In Internal IVA mode you cannot switch the camera to frozen kerbals. They're frozen! and their eyes don't work.
	+ You can switch around all the un-frozen kerbals seat cameras to take a look around.
	+ If you attempt to freeze a kerbal while in IVA mode the camera will automatically switch back to Flight mode.
	+ This is because the Kerbals want privacy while they get frozen.
	+ Snacks! - Vessel Supply screen now correctly updates to reflect number of active crew on-board.
	+ TAC LS - You still have to use my workaround re-build of TAC LS here.
	+ Remote Tech is now supported - Detects if RT is installed and if it is:-
	+ You cannot thaw kerbals unless you have active crew on-board or an active connection to your vessel if un-manned.
	+ When you attempt to freeze your last active crew on-board, you are given a warning that you will need
	+ an active crew on-board or active connection to thaw kerbals - you then have to click thaw a second time to confirm your action.
	+ Finally fixed Crew Xfers and seat allocations for frozen kerbals correctly.
	+ Added Temperature Checking function (switch on and off via config settings: RegTempReqd = true/false).
	+ If switched on the Freezer Part temperature must be < the RegTempFreeze value (in settings)to be able to freeze a kerbal.
	+ If switched on you must maintain the Freezer part temperature BELOW the RegTempMonitor (in settings) value.
	+ If you do not, then there is a good chance the freezer will fail and your kerbals WILL start dying.
	+ If switched on Freezing/Thawing and Holding Frozen Kerbals will cause the freezer parts to produce Heat which you will then
	+ need to manage.
	+ If you wish to use this function, do so at your own risk.. (or rather the Kerbals) and use a heat control mod and parts like
	+ http://forum.kerbalspaceprogram.com/threads/124391-1-02-Heat-Control-Manage-your-ship-s-heat!-%2815-06-2015-new-radiators-and-heat-exchangers%29
	+ Fixed the on-going ElectricCharge function. If you run out of ElectricCharge the freezer systems will go critical.
	+ A countdown timer will commence and when it finishes if you have not restored charge all your frozen Kerbals will DIE!!
	+ Updated the DeepFreeze GUI to include monitoring section for Temperature and EC if you have switched them on in the settings.
	+ Updated GUI to include scrollbars.
	+ Part config file for DeepFreezer partmodule now includes:-
		- GlykerolRequired = x - Amount of glykerol required to freeze a kerbal.
	+ Config/Settings file now includes the following new fields:-
		- ECReqdToFreezeThaw  = x  - The amount of ElecCharge required to Freeze or Thaw a Kerbal. This value will OVERRIDE the ChargeRequired field in any Part config file.
		- GlykerolReqdToFreeze = x - The amount of glykerol to Freeze a Kerbal. This value will OVERRIDE the GlykerolRequired field in any Part config file.
		- RegTempReqd = true/false - If true Regulated Part Temperatures are required to Freeze Kerbals and maintain them in frozen state.
		- RegTempFreeze = x - The Freezer part temperature must be < this for you to begin Freezing a Kerbal.
		- RegTempMonitor = x - The Freezer part temperature must remain < this for your Kerbals to remain frozen.
		- TempinKelvin = true/false - Will display temperature in the freezer part right click menu and the RegTempFreeze and RegTempMonitor values in Kelvin if true or Celcius if false.
	+ Now has a Config/Settings Window at the SpaceCenter that allows you to change the following config file settings from in-game.
	+ To access bring up the Deepfreeze Window at the Space Center by clicking the DeepFreeze App Icon and then click "settings" at the bottom of the window:-
			- ElectricCharge Required to run Freezers" = ECreqdForFreezer - Takes effect immediately.
			- AutoRecover Froen Kerbals at KSC" = AutoRecoverFznKerbals - Takes effect immediately.
			- Cost to Thaw a Kerbal at KSC" = KSCcostToThawKerbal - Takes effect immediately.
			- ElecCharge Reqd to Freeze/Thaw a Kerbal" = ECReqdToFreezeThaw - Takes effect immediately.
			- Glykerol Reqd to Freeze a kerbal" = GlykerolReqdToFreeze - Takes effect immediately.
			- Regulated Temperatures Required" = RegTempReqd - Takes effect immediately.
			- Minimum Part Temp. for Freezer to Freeze" = RegTempFreeze - Takes effect immediately. Only available if RegtempReqd is ON.
			- Maximum Part Temp. to Keep Kerbals Frozen" = RegTempMonitor - Takes effect immediately. Only available if RegtempReqd is ON.
			- Show Part Temperature in Kelvin" = TempinKelvin - Takes effect immediately.
			- Use Application Launcher (restart required)" = UseAppLauncher  - Requires RESTART to take effect.
			- Debug Mode" = debugging - Takes effect immediately.
	+ Issues with new release:
	+ Minor issue when transferring crew around sometimes makes the portrait cameras in the bottom right go black/blank.
	+ If you click on the arrows to scroll through the crew or switch view and back it fixes itself.
	+ Minor Issue/bug- Currently there is an issue with the internals when you have more than one freezer on the same vessel.
	+ During Testing - In this situation the Open/Closing of the Cryopods SOMETIMES gets confused and some of the empty pods appear frozen.
	+ Performance takes a hit when you have more than One freezer in a vessel, looking to optimize code in next update.
	+ To be investigated and updated/tuned for the next version, it is recommended until the next version that you refrain
	+ from having more than one freezer part per vessel.
	+ Issue with Stock Crew Transfers if you have Ship Manifest installed. If you have Ship Manifest installed use Ship Manifest
	+ for all crew transfers. For now if you have a vessel with a freezer part it will disable the Stock Xfer/EVA window (when you left click on a hatch).
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
