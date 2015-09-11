Config File Settings:   
Located in your install directory under \GameData\REPOSoftTech\DeepFreeze\Plugins\Config.cfg   
   
* DFwindowPosX, DFwindowPosY - the X,Y position of the DeepFreezer GUI window. Last position of the GUI is updated and saved here.   
* CFwindowPosX, CFwindowPosY - the X,Y position of the DeepFreezer GUI Settings window. Last position of the GUI is updated and saved here.   
* ECreqdForFreezer - set to True or False (Default). If True will require x units of Electrical Charge (x = value in FrzChargeRequired in part cfg file, default is10) per kerbal per minute to monitor their life support systems. If the vessel they are on runs our of EC the frozen kerbals will start dying.   
* UseAppLauncher - set to True (Default) or False. If True uses the stock KSP Application Launcher icons for the DeepFreeze GUI. If False will use Toolbar by blizzy (must be installed).   
debugging - Set to True or False (Default). If true spams the KSP Log with debug messages. (leave false)   
* AutoRecoverFznKerbals - Set to True (Default) or False. If True (Default) frozen kerbals will be thawed on vessel recovery automatically (for a cost, see next field). If False you have to thaw kerbals manually using the DeepFreeze GUI (for a cost, see next field).   
* KSCcostToThawKerbal - This is how much thawing a kerbal at the KSC costs (only valid in career games).   
* ECReqdToFreezeThaw = x - The amount of ElecCharge required to Freeze or Thaw a Kerbal. This value will OVERRIDE the ChargeRequired field in any Part config file.   
* GlykerolReqdToFreeze = x - The amount of glykerol to Freeze a Kerbal. This value will OVERRIDE the GlykerolRequired field in any Part config file.   
* RegTempReqd = true/false - If true Regulated Part Temperatures are required to Freeze Kerbals and maintain them in frozen state.   
* RegTempFreeze = x - The Freezer part temperature must be < this for you to begin Freezing a Kerbal.   
* RegTempMonitor = x - The Freezer part temperature must remain < this for your Kerbals to remain frozen.   
* heatamtMonitoringFrznKerbals - this is the amount of heat in Kilowatts generated per herbal to run the monitoring equipment. Is only relevant if RegTempReqd is set to on.   
* heatamtThawFreezeKerbal - is the amount of heat in Kilowatts generated per second when thawing or freezing a kerbal. Is only relevant if RegTempReqd is set to ON. Don't forget the new heat system in KSP, the amount of kW of heat is proportionate to the part's thermal mass.
* TempinKelvin = true/false - Will display temperature in the freezer part right click menu and the RegTempFreeze and RegTempMonitor values in Kelvin if true or Celcius if false.
* defaultTimeoutforCrewXfer = 30 - This is internal default timeout within DeepFreeze if a crew transfer fails to complete. Recommended you DO NOT change this.   
* cryopodResettimeDelay = 5 - This is internal default time delay for cryopod animation resets when crew are transferred or EVA/Board the vessel. Recommended you DO NOT change this.   
* DFWindowWidth = 420 - This is the default window width for the DeepFreeze main GUI screen.   
* CFWindowWidth = 340 - This is the default window width for the DeepFreeze Settings GUI screen.   
* KACWindowWidth = 485 - This is the default window width for the DeepFreeze Alarms GUI screen.
* ECLowWarningTime = 3600 - Time in Seconds before LOW EC warnings are given when EC monitoring/consumption function is on.   
* EClowCriticalTime = 900 - Time in Seconds before CRITICAL EC warnings are given when EC monitoring/consumption function is on.  
* StripLightsActive = True - If true Cryopod Strip lights will animate. If you have performance issues set this to false.   
* internalFrzrCamCode = 100 - this is the decimal ASCII code for the CameraMode Key, the default is 100 which is the 'd' key.   
* internalNxtFrzrCamCode = 110 - this is decimal ASCII code for the Next Freezer Camera Key, the default is 110 which is the 'n' key.   
* internalPrvFrzrCamCode = 98 - this is decimal ASCII code for the Previous Freezer Camera Key, the default is 98 which is the 'b' key.   
* The numeric values are from the standard ASCII key code table http://www.asciitable.com/    