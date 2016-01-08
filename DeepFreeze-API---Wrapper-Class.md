From v0.20.1.0 and onwards I have provided a wrapper file so that other mods can access DeepFreeze to interrogate the Frozen Kerbals Dictonary for a save game, view DeepFreezer part module information and even call Thaw/Freeze methods on a DeepFreezer part module. This can be used by other mods without the need to add a hard reference to my first DFInterface.DLL API. 

# Implementation Details
To access the API from your plugin is a couple of simple steps:

1. Add the DFWrapper.cs file to your project
[https://github.com/JPLRepo/DeepFreeze/blob/master/Source/DFWrapper.cs](https://github.com/JPLRepo/DeepFreeze/blob/master/Source/DFWrapper.cs)
2. Edit the Namespace definition at the top of the DFWrapper you have added to be specific to your plugin
Wrapper. 
3. Add a using statement to the top of your codefile to use your new namespace.
4. In the Update Method of your MonoBehaviour (or anytime after that) Initialise the wrapper. ie. you need to do this after KSP has awoken the DeepFreeze ScenarioModule DLLs (and only once), if you try and Init the wrapper in the Awake or Start method then the ScenarioModule may not be loaded. DFWrapper.InstanceExists indicates if the Initialize has already been successful or not.     


           
            if (!DFWrapper.InstanceExists)  // Check if DFWrapper has been initialized or not. If not try to initialize.  
            {    
                DFWrapper.InitDFWrapper();    
            }    
        
    

# Exposed Methods and Properties
The DFWrapper exposes - DeepFreeze itself (including the save game FrozenKerbals Dictionary) and a DeepFreezer class (replicating the DeepFreeze DeepFreezer PartModule class). The wrapper has XML commenting throughout so that the autocomplete text should prompt with suitable details.   

## DFWrapper
* (Boolean)AssemblyExists - True if the DeepFreeze DLL exists.   
* (Boolean)InstanceExists - True if the DeepFreeze API instance has been initialized.   
* (Boolean)APIReady       - True if the API instance has been initialized successfully and DeepFreeze is ready.   
* (DFAPI)DeepFreezeAPI    - This is the DeepFreeze Object that you can reference once initialized.  
* InitDFWrapper()         - Call to initialize the DeepFreezeAPI object. 

## DFAPI
* (Boolean)APIReady                             - True if the real APIReady field is true in DeepFreeze object.
* (Dictionary<string, KerbalInfo>)FrozenKerbals - A dictionary containing all the Frozen Kerbals in the current save game.    

## KerbalInfo
* (double)lastUpdate                   - game time the FrozenKerbalInfo was last updated.
* (ProtocrewMember.RosterStatus)status - RosterStatus of the frozen kerbal.
* (ProtoCrewMember.KerbalType)type     - KerbalType of the frozen kerbal.
* (Guid)vesselID                       - Guid of the vessel the frozen kerbal is aboard.
* (string)vesselName                   - Name of the vessel the frozen kerbal is aboard.
* (uint)partID                         - partID of the vessel part the frozen kerbal is aboard.
* (int)seatIdx                         - seat index that the frozen kerbal is in.
* (string)seatName                     - seat name that the frozen kerbal is in.
* (string)experienceTraitName          - name of the experience trait for the frozen kerbal.

## DeepFreezer
### Vars/Properties
* (Boolean)crewXferTOActive    - True if a crew transfer TO this freezer is currently active (a thaw/freeze process cannot run while a crew transfer is active).
* (Boolean)crewXferFROMAtive   - True if a crew transfer FROM this freezer is currently active (a thaw/freeze process cannot run while a crew transfer is active).
* (int)FreezerSize             - The total number of seats (cryopods) in this freezer.
* (int)TotalFrozen             - How many frozen kerbals there are currently in this freezer.
* (int)FreezerSpace            - Indicates how many empty freezers there are currently in the freezer part (takes into account frozen kerbals).
* (Boolean)PartFull            - True if the part is full (includes thawed and frozen crew in the part).
* (Boolean)IsFreezeActive      - True when this freezer is currently running a Freeze Kerbal process (only one thaw or freeze can run on each freezer at a time).
* (Boolean)IsThawActive        - True when this freezer is currently running a Thaw Kerbal process (only one thaw or freeze can run on each freezer at a time).
* (Boolean)FreezerOutofEC      - True if the freezer requires Electrical Charge (has frozen kerbals) and cannot get any EC.
* (FrzrTmpStatus)FrzrTmp       - FrzrTmpStatus is an Enum (OK, WARN, RED) indicating the Freezer temperature status.
* (FrznCrewList)StoredCrewList - A List<FrznCrewMbr> of Frozen Crew members in the part.  

### Methods
* (Boolean)beginFreezeKerbal(ProtoCrewMember CrewMember) - Starts a Freeze process on CrewMember. CrewMember must be set to ProtoCrewMember that is inside the freezer part. Returns a boolean indicating the success of the call (not the success of the freeze).
* (Boolean)beginThawKerbal(string frozenkerbal) - Starts a Thaw process for frozenkerbal. frozenkerbal must be set to the kerbal's name that is currently frozen inside the part. Returns a boolean indicating the success of the call (not the success of the freeze).

## FrznCrewMbr
* (string)CrewName    - Crew member name.
* (int)SeatIndx       - Seat index.
* (Guid)VesselD       - Vessel ID.
* (string)VesselName  - Vessel Name.

# Example Code
You can see an example of how to use the API in the code in the DFAPITester Project, which can be found here:
[https://github.com/JPLRepo/DeepFreeze/tree/master/Source/DeepFreeze_APITester](https://github.com/JPLRepo/DeepFreeze/tree/master/Source/DeepFreeze_APITester)