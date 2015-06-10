# DFInterface.dll

Deep Freeze provides an interface to allow for detection of Frozen Crew. 
As KSP OutOfTheBox (OOTB) does not support FROZEN kerbals Deepfreeze had to come up with a way of setting a Kerbal up to appear Frozen and 'trick' the game and other mods into not seeing the frozen kerbals.  
A much better approach would be that KSP did support other statuses... Wishful thinking.  
The next best thing is  this interface which other Mods can use to know which Kerbals are frozen or not.  
The next best thing after using this interface is to just guess if DeepFreeze is installed and do your own checking for frozen kerbals.  
If you don't want to use this interface and do your own checking DeepFreeze tricks KSP for Frozen KErbals by setting they type = Unowned (usually this is Crew) and rosterstatus = Dead (usually Assigned). 
DeepFreeze then actually REMOVES the Kerbal from the vessel/part  so they are not included in part counts, crew list, etc. DeepFreeze DOES remember the vessel/part/seat details for them (which you can get via this interface) so when they are Thawed again their settings are all reset and they are re-added into the vessel/part.  
The last thing would be to do nothing and be ignorant of frozen kerbals (but then you probably wouldn't be reading this page).  

This interface exposes the details of all frozen kerbals.  

It contains the following Methods:  
**IsDFInstalled** - returns a Bool value indicating if DeepFreeze is installed or not.  
**GetFrozenKerbals()** - Exposes a C# dictionary <String, KerbalInfo> using a String for the  Key which is set to each Frozen Kerbal's full name. The dictionary Value is set to a type KerbalInfo (details below) which exposes various details about each frozen Kerbal.
If a Kerbal is FROZEN they appear in this dictionary. If they are NOT Frozen, they don't.

## Accessing DFInterface

The DFInterface.dll is designed to reside in your plugins folder. Create a reference to the dll in your source/project, and then make a call to interrogate the provided bool IsDFInstalled to determine if Deep Freeze is installed. Once you have established that DeepFreeze is installed you can then call GetFrozenKerbals() to obtain an instance of the IDFInterface Object for your use.

Sample Calling Code:  

    `
     private bool IsDFInstalled = false;  
     IsDFInstalled = DF.DFInterface.IsDFInstalled;  
     if (IsDFInstalled)  
     {  
         DF.IDFInterface DFOjbect = null;   
         try  
         {  
             DFOjbect = DF.DFInterface.GetFrozenKerbals();  
  	     foreach (KeyValuePair<string, DF.KerbalInfo> frznCrew in DFOjbect.FrozenKerbals)  
	     {  
                ........YOUR SPECIFIC MOD CODE WITH RELATION TO DEEPFREEZE PROCESSING....  
             }  
         }  
         catch (exception ex)  
	    + {
	    + Debug.Log("Error attempting to check DeepFreeze for FrozenKerbals");
	    + Debug.Log(ex.Message);
	    + }
	    + }
    }  
`

## GetFrozenKerbals() attributes
This interface exposes several properties via the KerbalInfo type for third party mod use. They are explained below.  
double **lastUpdate** - The game time (Planetarium.GetUniversalTime) the Kerbal was Frozen.  
ProtoCrewMember.RosterStatus **status** - Their Roster Status which is set to DEAD when they are frozen.  
ProtoCrewMember.KerbalType **type** - Their Kerbal Type which is set to UNOWNED when they are frozen.  
Guid **vesselID** - the Guid vessel.id of the Vessel they are currently assigned to as frozen.  
string **vesselName** - The name of the Vessel they are currently assigned to.  
uint **partID** - The partid - flightid unique part ID of the actual freezer part they are frozen within.  
int **seatIdx** - The seat index they are assigned to within the part.  
string **seatName** - The seat transform name of the seat they are assigned to within the part.  
string **experienceTraitName** - Their experience trait name (pilot, engineer, etc).  

The source code for the dll can be found [here](https://github.com/JPLRepo/DeepFreeze/tree/master/Source/DFInterface).  
The DLL itself can be found [here](https://github.com/JPLRepo/DeepFreeze/tree/master/DFInterface/Plugins)

