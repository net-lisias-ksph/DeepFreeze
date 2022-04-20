# Deep Freeze :: Change Log

* 2016-0430: 0.22.1.0 (JPLRepo) for KSP 1.1.2
	+ V0.22.1.0 "KSP 1.1.2 Update"
	+ Fixed portrait camera issues.
	+ Fixed On-Screen messages for Kerbal Name when in Alternate - Cryopod Camera mode.
	+ Fixed spacing (scroll lists) in the DeepFreeze GUI menus.
	+ Fixed switching from Stock Toolbar Icon to Blizzy Toolbar Icon and back again.
	+ Made Settings Menu resizable.
	+ Added some more KSPedia pages - What do people want to see here?
* 2016-0424: 0.22.0.0 (JPLRepo) for KSP 1.1.1
	+ Added first-cut KSPedia Pages - this is really just testing out this feature and is a very rough first cut. Plans to expand and improve this.
	+ Support for NEW RPM - JSIAdvTransparentPods - no longer supports the OLD RPM TJSITransparentPods. You need RPM - JSITransparentPods V0.25.0 or above.
	+ Support for Kerbalism Mod.
	+ Minor Bugs (fix in next version):
	+ 1) When you freeze/thaw from internal cam (alternate camera) the camera loses the transform reference point at the end of the process.
	+ 2) When inside the CRY-0300 with the External Doors closed, if you zoom out strange camera effects mean the door is only partially visible.
	+ 3) The screen messages when in Cryopod-Camera mode are not showing all the kerbal's names.
	+ 4) When you change settings from Stock to Toolbar and change scenes, the toolbar appears, but stock button is still there. A restart or several scene changes fixes it.
	+ 5) When there is a Kerbal on the ladder in front of the CRY-0300 and the doors are open the Internal Overlays the kerbal and blocks them from view.   This is actually an RPM - JSIAdvTransparentPods bug.
	+ 6) The CRY-0300R has lost it's ability to show cool Window Freeze/Thawing animation effects.
	+ Issues with release:
	+ Background Processing is not available under KSP 1.1. Unless the mod author updates it soon I will look to put my own EC background processing into DeepFreeze. For now if you are using EC usage the non-Background Processing method still works (it plays catch-up when you swith to the vessel).
	+ There is no version of TAC LS for KSP 1.1 - so it is not currently supported.
* 2016-0315: 0.20.4.0 (JPLRepo) for KSP 1.0.5
	+ Fixed bug when using EC for frozen kerbals is turned ON and BackgroundProcessor is not installed. When you switch back to a vessel after a long period of time and you don't have enough EC to catch-up on the EC usage DeepFreeze was not correctly consuming 95% of remanining EC and was executing the Kill/Emergency Thaw procedure.
	+ Fixed GUI when EC usage is on where the fields were not spanning the resizable window correctly.
	+ Improved error handling for a spurious bug in Tracking Station that cannot be tracked down.
	+ Removed DFInterface.DLL API. Wrapper API now provided for other Mods to interface to DeepFreeze.
	+ Removed use of SMInterface.DLL API to interface to Ship Manifest. Replaced with Reflection Wrapper class. Requires Ship Manifest V5.0.1.0 or above.
	+ Changed DEFAULT CLS setting for the CRY-0300 and CRY-0300R to be Passable (allowing unrestricted crew transfers), this is due to a known bug in CLS/Ship Manifest mods.
	+ Will change this setting back once Papa_Joe fixes that bug in CLS/SM.
	+ Earlier versions of Ship Manifest no longer supported.
	+ Updated Mini-AVC included to newer version to stop log spam.
	+ Added Community Tech Tree science node definitions (via Module Manager file, requires Module Manager).
	+ Re-Factored a lot of code and utilities (Code Housekeeping).
* 2016-0214: 0.20.3.0 (JPLRepo) for KSP 1.0.5
	+ V0.20.3.0 "bug Fixes"
	+ Fixed bug when thawing some kerbals vessel where vessel reference transform was not set in some cases.
	+ Modified debugging and error messages during thawing to assist easier bug hunting in the future.
* 2016-0127: 0.20.2.0 (JPLRepo) for KSP 1.0.5
	+ Fixed null ref bug when vessels are destroyed.
	+ Fixed null ref bug when KSP vessel list cannot be accessed.
	+ Fixed null ref/NAN bug when revert to editor (from vessel with DeepFreeze part) and launch another vessel.
* 2016-0107: 0.20.1.0 (JPLRepo) for KSP 1.0.5
	+ Fixed sound glitch/issue with CRY-0300R when attaching more than one in symmetry mode in the editor.
	+ For Other Modder/Mods API interface re-written providing API via reflection class (no hard dependency) - of no relevance to users.
* 2015-1208: 0.20.0.0 (JPLRepo) for KSP 1.0.5
	+ Added new Radial External Cryopod - The CRY-0300R. A single kerbal Cryopod part that can be radially attached. The CRY-0300R also has an attach point at the top of the pod.
	+ Great for adding radial pods to your vessel or inside a SpacePlane CargoBay! Fits inside the Mk-2 & Mk-3 Cargo bays, the part does clip through the base of cargo bays as it is primarily designed to attach to the outside of a curved part.    However, if you get creative you can fit it into a Cargo bay using girders or octaganol struts.
	+ The CRY-0300R supports RasterPropMonitor transparent pods (yes it's transparent if you have RPM installed).
	+ The CRY-0300R also has an external EVA hatch. The CRY-0300R only weighs 0.87t (the full CRY-0300 weights 2.62t) and appears in the TechTree at spaceExploration (same as the CRY-0300).
	+ This now completes the set of all the originally planned DeepFreeze parts.
	+ MerlinsMaster has re-textured more details into all the Cryopods.
	+ Fixed Pod transparency for the CRY-0300 (and the CRY-0300R) based on RPM transparency setting in flight and also now works in the Editor (VAB/SPH). However, due to the complications of DeepFreeze parts transparency can either be ON or OFF (RPM AUTO setting is treated as Transparency OFF).
	+ Fixed bug where the External Door Open/Close sound effect was not working for the CRY-0300.
	+ Rationalis(z)ed all the part models and textures into one folder, as a lot of them are shared. This will save some memory.    Thanks goes to khr15714n for kicking me into doing this as I have been meaning to for a while.
	+ Due to this however, if you are upgrading from a previous version of DeepFreeze you MUST delete the /GameData/REPOSoftTech/DeepFreeze entirely BEFORE installing this version. If you want to save your DeepFreeze
	+ settings make a backup/copy of /GameData/REPOSoftTech/DeepFreeze/Plugins/Config.cfg file BEFORE deleting your DeepFreeze folder then copy you backup/copy of this file back into the /GameData/REPOSoftTech/DeepFreeze/Plugins folder once you have upgraded.
* 2015-1110: 0.19.3.0 (JPLRepo) for KSP 1.0.5
	+ Recompile for KSP 1.0.5
* 2015-1030: 0.19.2.0 (JPLRepo) for KSP 1.0.3
	+ Fix distribution to include missing Editor group icon from V0.19.0.0 that somehow got left out of V0.19.1.0.
	+ Fix bug that V0.19.2.0 introduced that was causing invalid seat placements and
	+ Add more robust checking of Seat placements for frozen kerbals to avoid bugs that have been occurring for some users.
	+ Fix seat placement when a freeze/thaw process is aborted.
* 2015-1019: 0.19.1.0 (JPLRepo) for KSP 1.0.3
	+ Added comatose function for when EC or Heat options are ON and Fatal option is OFF. Now when you run out of EC or overheat with these options set kerbals will be emergency thawed
	+ and become comatose (tourists) for a period of 5 minutes (can be changed in the settings menu).
	+ Fixed bug with new pop-up windows when EC is critical or overheat - this pop-up will now NOT appear if the active vessel is the vessel that has run out of EC or overheat.
* 2015-1007: 0.19.0.0 (JPLRepo) for KSP 1.0.3
	+ Added Fatal EC/Heat option. If this is ON kerbals will die if EC runs out or it gets too hot (if you are using the EC and Heat options). If this is OFF
	+ the Kerbals will be emergency thawed and become available again, and start consuming LS resources again. (to-do - expand this to perhaps make them unusable for a period of time due to
	+ emergency thaw effects, but not in this version) Default setting (for compatibility) is set to ON. - IE: running out of EC or over-heating will Kill kerbals.
	+ Added pop-up window when EC is critical for vessels that are not the active vessel and you can automatically switch to that vessel.
	+ Added flatline sound effect if kerbals die due to lack of EC or over temperature condition.
	+ Support for Texture Replacer V2.4.10, you MUST have this version (or above) of Texture Replacer installed.    Thawed kerbals will no longer lose their customised texture settings.
	+ Support for RasterPropMonitor V0.23.0, you MUST have this version (or above) of RPM installed.
	+ Changed the Editor Icon for DeepFreeze parts category to use Snowflake/Freeze icon instead of EVA Kerbal (stock) icon.
	+ Added Engineer Info report check where there is a DeepFreeze Freezer attached that the vessel has 5 or more units of Glykerol available.
	+ Fixed Engineer report in editor so that DeepFreeze Freezers are now considered parts that use Glykerol and ElectricCharge.
	+ Fixed bug where ships docking/un-docking with frozen kerbals results in unable to thaw frozen kerbals.
	+ Fixed bug in new Internal Camera system when swapping to other DeepFreeze vessels that are in range the cameras do not move/update to the correct vessel.
	+ Fixed bug if you have multiple vessels in loaded range on initially switching to flight mode on one vessel, if you swap to a DeepFreeze equipped vessel (with DeepFreeze part) and you attempt to thaw a previously frozen
	+ kerbal, the thaw may not work or it will work but the kerbal is not visible on thawing.
	+ Fixed issue where a freeze/thaw is in progress and the player switches vessels. DeepFreeze will now abort any in-progress thaw/freeze in this case.
	+ Fixed NullReference bug in DFIntMemory with the internal cameras function.
* 2015-0930: 0.18.2.2 (JPLRepo) for KSP 1.0.3 PRE-RELEASE
	+ V0.18.3.0 "Bug fixes & Enhancements"
	+ Added Fatal EC/Heat option. If this is ON kerbals will die if EC runs out or it gets too hot (if you are using the EC and Heat options). If this is OFF the Kerbals will be emergency thawed and become available again, and start consuming LS resources again. Defaults to ON.
	+ Fixed issue where a freeze/thaw is in progress and the player switches vessels. DeepFreeze will now abort any in-progress thaw/freeze in this case.
	+ Added flatline sound effect if kerbals die due to lack of EC or over temperature condition.
	+ Fixed NullReference bug in DFIntMemory with the internal cameras function.
	+ Support for Texture Replacer V2.4.10, you MUST have this version of Texture Replacer installed. Thawed kerbals will no longer lose their customised texture settings.
	+ Support for RasterPropMonitor V0.23.0, you MUST have this version of RPM installed.
* 2015-0911: 0.18.2.1 (JPLRepo) for KSP 1.0.3
	+ Fix release - add missing DFInterface.DLL file to distro.
* 2015-0911: 0.18.2.0 (JPLRepo) for KSP 1.0.3
	+ V0.18.2.0 "Bug Fixes & Enhancements"
	+ Fix Radial attachment points for CRY-0300 exclusion zones around the external doors. The CRY-0300 now correctly allows you to attach radial parts to the outside of it except for where the external doors are.
	+ There is a EVA Access point at the bottom of the external doors. If you block this with radial parts your EVA access will be blocked by KSP and you will get the "Hatch Obstructed" message.
	+ It is recommended you do not attach parts to the doors or the lower front section of the CRY-0300.
	+ Fix DeepFreeze partmodule to support re-use on non DeepFreeze parts. To use you must add partmodule to a crewable part but you must NOT have an internalmodel defined for that part.
	+ Refer to the WIKI page on how to configure your own parts (WARNING: No support will be provided for parts you have made yourself using this method).
	+ All Cryopods now have windows that freeze and thaw (as was our original intent) so they go transparent when empty or a thawed kerbal is seated, and they appear frozen when a frozen kerbal is within.
	+ You can now switch to Internal Cameras (same cameras used when in IVA and you freeze/thaw a Kerbal) using Modifier key (Windows this is ALT) and d key.
	+ Switch to the next Cryopod Internal Camera using the 'n' key. Switch to the previous Cryopod Internal Camera using the 'b' key.
	+ Press the 'c' or whatever key you have mapped to camera to switch back to IVA/Flight Camera mode.
	+ You can change the key settings in the \GameData\REPOSoftTech\DeepFreeze\Pluginf\Config.cfg file using a text editor (not available via the in-game settings menu).
	+ internalFrzrCamCode = 100 - this is the decimal ASCII code for the CameraMode Key, the default is 100 which is the 'd' key.
	+ internalNxtFrzrCamCode = 110 - this is decimal ASCII code for the Next Freezer Camera Key, the default is 110 which is the 'n' key.
	+ internalPrvFrzrCamCode = 98 - this is decimal ASCII code for the Previous Freezer Camera Key, the default is 98 which is the 'b' key.
	+ The numeric values are from the standard ASCII key code table http://www.asciitable.com/
	+ Minor adjustments to the CRY-2300 and CRY-1300 Internal models.
	+ Tweaks to the animations - on vessel load pod window states are set immediately, before it used to run the animation loops. The same for when a freeze or thaw event fails.
	+ The Freeze and Thaw Process have been tweaked: On initiating a Freeze or Thaw process the Pod will first Charge the required EC before executing the freeze or thaw process.
	+ New sound effect for charging the Pod EC on Freeze and Thaw. Monitoring equipment sound effect when in IVA/Internal view mode.
* 2015-0823: 0.18.1.0 (JPLRepo) for KSP 1.0.3
	+ Fix GUI LastTimeUpdated field to stop tracking time when settings are changed to turn off ECreqd/Monitoring option.
	+ Fix GUI Colours for EC monitoring, Temp Monitoring and LastTimeUpdated field.
	+ Fix error accessing Kerbal Alarm Clock entries with invalid vessel id's (alarms not attached to vessels) and reduce log spam.
	+ Fix Error in Texture assignments for models.
	+ Fix error loading/saving cryopod states on part load/save.
	+ Fix CRY-0300 transparency issue for some users.
* 2015-0822: 0.18.0.0 (JPLRepo) for KSP 1.0.3
	+ Refer to the changelog on the [Forum here](http://forum.kerbalspaceprogram.com/threads/124720). There are just so many changes.
* 2015-0712: 0.17.1.0 (JPLRepo) for KSP 1.0.3
	+ Introducing the New CRY-1300 3-Kerbal capacity 2.5M Freezer part (hitchhiker sized).
	+ Contains 3 DeepFreeze Cryogenic Cryopods and a Glykerol Tank (capacity 15 Glykerol units).
	+ New Part at specialized Construction in TechTree.
	+ Moved Cry-2300 10 kerbal Freezer to advanced Metalworks in TechTree.
	+ Re-factored Parts Directories, if upgrading please Delete \GameData\REPOSoftTech\DeepFreeeze
	+ before installing.
* 2015-0706: 0.17.0.0 (JPLRepo) for KSP 1.0.3
	+ Finalization of the Large Internal, and set-up for all the up-coming parts (as they will use the same base code and animations).
	+ Yes - Animated Cryopods! See for yourself. When you Freeze or Thaw from external view, you will see the Pod open/close in the portrait cameras.
	+ If you are in IVA/Internal mode when you freeze/thaw the camera will switch to an internal camera viewing the pod of the kerbal you are about to freeze/thaw.
	+ It will then animate open/close of the cryopod. This is in place of kicking you out to flight view and removing/replacing the Cryopod windows (which it was doing in previous version).
	+ Fixed Issue with USI LifeSupport consuming resources on thaw of kerbals. DeepFreeze will detect if USI LS is installed and remove tracking in USI LS for kerbals when they are frozen.
	+ (Same Issue as TAC LS, but can fix this one in DeepFreeze without waiting for author of other mod to change).
	+ Fixed attach point for the external Glykerol Tank.
	+ Changed the Cry-2300 Internal Glykerol tank to store 50units of Glykerol (instead of 40).
	+ This allows you to Freeze 10 kerbals (the part capacity) ONCE without the need for external tanks.
	+ Converted all textures to DDS format.
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
