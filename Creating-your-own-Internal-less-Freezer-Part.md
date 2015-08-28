Let's say you want to create your own custom DeepFreeze Continued... part.   
For whatever reason you have, given the glorious internal parts and models MerlinsMaster has created do not suit your needs.   
You can create your own part, however, your part will have NO internal model, cryopods and all the other cool stuff inside.  
OK, you still want to create one. Here is how. WARNING - NO support will be provided for parts you create yourself beyond this WIKI page. If you can't follow these instructions you probably shouldn't be doing this. If you mess up and kill your crew or your save game you have been warned.  
 
* Create a new folder in <KSPinstalldir>\GameData\REPOSoftTech\DeepFreeze\Parts\<yournewpartfolder>   
* Copy an existing parts files into this folder. For our example let's use the KSP Stock Hitchhiker can and let's make it a 6 kerbal DeepFreeze part (with no internal).   
* So I copy **ALL** of the files in <KSPinstalldir>\GameData\Squad\Parts\Command\hitchhikerStorageContainer\*.* into the folder I just created above. Or, I just copy the whole hitchhikerStorageContainer folder into my \DeepFreeze\Parts\ folder.    
   
* Now Edit the hitchhikerStorageContainer.cfg file in your new copy directory using any text editor.   

You must change the following fields in the config file:    
1. name = crewCabin - Change crewCabin to something unique. It must be unique across all your installed parts.   
2. CrewCapacity = 4 - We want a 6 kerbal freezer so we change this to CrewCapacity = 6.   
3. title = xxxx = Change the title to your own name. This is what shows in the VAB as the name of your part.   
4. Change the manufacturer = and description = to whatever you like.   
* **REMOVE** the following lines (your must have no INTERNAL node in the config file or this will not work).   
```   
    INTERNAL
        {        
            name = crewCabinInternals      
        }      
```      
   
**ADD** a new MODULE node at the end of the config file **BEFORE** the last }.   
   
`   
MODULE   
    {      
        name = DeepFreezer   
        FreezerSize = 6   
        ChargeRequired = 3000   
        GlykerolRequired = 5   
        ChargeRate = 30   
        FrznChargeRequired = 10   
        isPartAnimated = False   
        cryopodstateclosedstring = True, True, True, True, True, True   
    }   
`   

* SAVE your edited config file.   
It should look like this from our example (of course you will have whatever you came up with for your name, title, manufacturer, and description fields):   
`   
PART   
{   
	name = dodgyFreezer   
	module = Part   
	author = NovaSilisko   
	mesh = model.mu   
	rescaleFactor = 1   
	node_stack_top = 0.0, 0.986899, 0.0, 0.0, 1.0, 0.0, 2   
	node_stack_bottom = 0.0, -0.986899, 0.0, 0.0, -1.0, 0.0, 2   
	CrewCapacity = 6   
	TechRequired = spaceExploration   
	entryCost = 12400   
	cost = 4000   
	category = Utility   
	subcategory = 0   
	title = My Dodgy DeepFreeze Part   
	manufacturer = Dodgy Parts Co   
	description = This is my dodgy DeepFreezer 6 kerbal part. It has no internal. Sob sob... I should just use the cool DeepFreeze continued supplied parts.   
	attachRules = 1,0,1,1,0   
	mass = 2.5   
	dragModelType = default   
	maximum_drag = 0.2   
	minimum_drag = 0.3   
	angularDrag = 2   
	crashTolerance = 6   
	breakingForce = 200   
	breakingTorque = 200   
	maxTemp = 2000 // = 2900   
	vesselType = Ship   
	bulkheadProfiles = size2   
	   
	MODULE   
	{   
		name = ModuleScienceExperiment   
		experimentID = crewReport   
		experimentActionName = Crew Report   
		resetActionName = Discard Crew Report   
		reviewActionName = Review Report   
		useStaging = False   
		useActionGroups = True   
		hideUIwhenUnavailable = True   
		rerunnable = True   
		xmitDataScalar = 1.0   
		usageReqMaskInternal = 5   
		usageReqMaskExternal = -1   
	}   
	MODULE   
	{   
		name = ModuleScienceContainer   
		reviewActionName = Review Stored Data   
		storeActionName = Store Experiments   
		evaOnlyStorage = True   
		storageRange = 2.0   
	}   
	MODULE   
	{   
		name = FlagDecal   
		textureQuadName = flagTransform   
	}   
	MODULE   
	{   
		name = DeepFreezer   
		FreezerSize = 6   
		ChargeRequired = 3000   
		GlykerolRequired = 5   
		ChargeRate = 30   
		FrznChargeRequired = 10   
		isPartAnimated = False   
		cryopodstateclosedstring = True, True, True, True, True, True   
	}   
}   
`   
You can remove the ModuleScienceExperiment, ModuleScienceContainer MODULE nodes if you want.   
You can repeat the process if you like. If you want a different crew capacity you simply change the    
* CrewCapacity = x - what crew capacity you want.
* FreezerSize = x - must be the same as CrewCapacity.
* cryopodstateclosedstring = True, True, etc - There should be the same number of "True, " as the Crewcapacity.   

