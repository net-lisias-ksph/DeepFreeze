From v0.20.1.0 and onwards I have provided a wrapper file so that other mods can access DeepFreeze to interrogate the Frozen Kerbals Dictonary for a save game, view DeepFreezer part module information and even call Thaw/Freeze methods on a DeepFreezer part module. This can be used by other mods without the need to add a hard reference to my first DFInterface.DLL API. 

# Implementation Details
To access the API from your plugin is a couple of simple steps:

1. Add the DFWrapper.cs file to your project
<insert link here>
2. Edit the Namespace definition at the top of the DFWrapper you have added to be specific to your plugin
Wrapper. 
3. Add a using statement to the top of your codefile to use your new namespace.
4. In the Update Method of your Monobehaviour (or anytime after that) Initialise the wrapper. ie. you need to do this after KSP has awoken the DeepFreeze ScenarioModule DLLs, if you try and Init the wrapper in the Awake or Start method then the ScenarioModule may not be loaded.  

<code>   
if (!DFWrapper.InstanceExists)  // Check if DFWrapper has been initialized or not. If not try to initialize.
{
     DFWrapper.InitDFWrapper();                
}
internal override void Start()
</code>   

# Exposed Methods and Properties