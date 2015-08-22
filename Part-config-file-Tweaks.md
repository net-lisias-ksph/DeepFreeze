Part Tweaks (for advanced users):   
* Glykerol storage can be changed on the radial tank and the cryofreezer by changing the RESOURCE node amount and maxamount field value.   
In the freezer part the DeepFreezer MODULE has the following values:-    
* GlykerolRequired = x - Amount of glykerol required to freeze a kerbal.   
* FreezerSize = 10 - This is how many kerbals can be frozen in the part. Make sure you change the CrewCapacity value to be the same or results will be totally unpredictable.   
* ChargeRequired = 3000 - This is the amount of EC required to freeze or thaw a kerbal.   
* ChargeRate = 30 - this is how fast a kerbal is frozen or thawed, consuming 30 EC per Unity physics frame until the * ChargeRequired is met then your kerbal is done.   
* FrzChargeRequired = 10 - This is the amount of EC you need ot keep a kerbal alive per minute. (you must set ECreqdForFreezer to True in the mod config file (see section above). If ECreqdForFreezer is Fase this value is not used by the part.   
