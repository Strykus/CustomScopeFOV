# CustomScopeFOV

Adding Custom fully customizable FOV and FOV Viewmodel settings for each scope separately, custom scopes for sniper, effects for projectile and several view models presets
And fixing iron sight position for Hemlok in Titanfall 2

![CustomScopeFOV](https://user-images.githubusercontent.com/37307454/152735702-051a48e8-570a-4311-99c9-67ece629cbf6.png)


## INSTALLATION

This mod is compatible with:

[VTOL](https://github.com/BigSpice/VTOL) and [Thunderstore](https://northstar.thunderstore.io/) You can use one of those to install the mod

Or going on the GitHub page on [Release](https://github.com/Strykus/CustomScopeFOV/releases) section 

## File location and Overview

1: Go to `~/Titanfall2/R2Northstar/mods/CustomScopeFOV/mod/scripts/weapons/mp_<name of the weapon/weapon type>_fov.txt`


2: When opening file you will see something like this: 

From the start we can chose one of many pre made viewmodel_offset for hipfire

    WeaponData
    {
	MP_BASE
	{
		// Default: "0 0 0" // hipfire viewmodel that you can change how you like (-left/x/right front/z/-back up/y/-down)
		"viewmodel_offset_hip" "2.5 -2 -3" //my preference
		//"viewmodel_offset_hip" "-8.5 -2 -3" //my preference but who want it be on the left side
		//"viewmodel_offset_hip" "-3 3 -3" //DOOM like viewmodel
		//"viewmodel_offset_hip" "-3 -40 -3" //clear view
		//"viewmodel_offset_hip" "2 3 3" //gangsta style
		//"viewmodel_offset_hip" "-8 3 3" //gangsta style left handed


			"dof_zoom_nearDepthStart"						"0.0" //remove dof for iron sight
			"dof_zoom_nearDepthEnd"							"0.0"

			dof_zoom_focusArea_horizontal					0.0
			dof_zoom_focusArea_top							0.0
			dof_zoom_focusArea_bottom						0.0

In this part we can change our viewmodel_offset_hip that have several presets
and at the end here we can change `zoom_fov` - fov while ADS and `zoom_fov_viewmodel` - fiew model fow while ADS when ads for iron sight specifically

	}



			"zoom_fov"		    	"40" //edit iron sight fov here
			//"zoom_fov_viewmodel"		    	"40"//edit iron sight fov viewmodel here

In this part we can change our viewmodel_offset_hip that have several presets
and at the end here we can change `zoom_fov` - fov while ADS and `zoom_fov_viewmodel` - fiew model fow while ADS when ads for iron sight specifically
you need to remove `"//"comments` to made value work or add `"//"` if you want value to stop affect this settings


## How To Modify Specific Scope
By scrolling down in our txt file we will see this:
 This is where we can change fov in ADS and FOV of viewmodel for each scopre that weapon have specificaly
 Near values was named in game name of the each scope, so you know what exact scope you want to modify
  Just change value to what you like and ofc remove `"//"`
  In front of the value so changes will apply inside the game

    {
    	"zoom_fov"		    	"55"  //this value will be active in game
    	//"zoom_fov_viewmodel"		    	"40"  //this value will not be active in the game
    }
![AlternatorFOV](https://user-images.githubusercontent.com/37307454/152891537-3b2bc12b-1962-4c2b-8e29-8b69bfacd330.gif)

  Just change value to what you like and ofc remove `"//"`
  In front of the value so changes will apply inside the game

	Mods //Alternator bellow you can chagne fov("zoom_fov" or "zoom_fov_viewmodel") for each scope that you want, and change iron_sight fov in the value above this comment
	{
		iron_sights
		{
		}
		hcog //HCOG
		{

			"dof_zoom_nearDepthStart"						"0.0"
			"dof_zoom_nearDepthEnd"							"0.0"

			"zoom_fov"		    	"55"
			//"zoom_fov_viewmodel"		    	"40"
			dof_zoom_focusArea_horizontal					0.0
			dof_zoom_focusArea_top							0.0
			dof_zoom_focusArea_bottom						0.0
		}
		holosight // ignore this one
		{

			"dof_zoom_nearDepthStart"						"0.0"
			"dof_zoom_nearDepthEnd"							"0.0"

			"zoom_fov"						"45"
			//"zoom_fov_viewmodel"		    	"55"
			dof_zoom_focusArea_horizontal					0.0
			dof_zoom_focusArea_top							0.0
			dof_zoom_focusArea_bottom						0.0
		}
		redline_sight //HCOG Ranger
		{

			"dof_zoom_nearDepthStart"						"0.0"
			"dof_zoom_nearDepthEnd"							"0.0"

			"zoom_fov"						"45"
			//"zoom_fov_viewmodel"		    	"45"
			dof_zoom_focusArea_horizontal					0.0
			dof_zoom_focusArea_top							0.0
			dof_zoom_focusArea_bottom						0.0
		}
		threat_scope //Threat Scope
		{
			"dof_zoom_nearDepthStart"						"0.0"
			"dof_zoom_nearDepthEnd"							"0.0"

			"zoom_fov"						"20"
			//"zoom_fov_viewmodel"		    	"55"
			dof_zoom_focusArea_horizontal					0.0
			dof_zoom_focusArea_top							0.0
			dof_zoom_focusArea_bottom						0.0
		}
	}

## Custom projectile trails

Here in `mp_kraber_fov.txt` we can find this values by scrolling at the end of the document
 Just decomment "//" effect that you like

 			//"projectile_trail_effect_0" 					"P_mastiff_proj_amp"// Amped Mastiff trail effect //this effect will not be active
			"projectile_trail_effect_0" 					"P_plasma_proj_LG_amp"// Amped EPG trail //this effect will be active

 And apply it  by saving file and restarging mod by using command in sonsole `sv_cheats 1; weapon_reparse; reload_mods; sv_cheats 0` while in main menu lobby or where you can activate `sv_cheats 1`
  # NOTE: `Can be applied one "projectile_trail_effect_0" at the time`

			//bellow is settings for Kraber projectile change, remove "//" before "projectile_trail_effect_0" to made this effect active	
			//And reload mod

			//"projectile_trail_effect_0" 					"P_mastiff_proj"// Mastiff trail effect
			//"projectile_trail_effect_0" 					"P_mastiff_proj_amp"// Amped Mastiff trail effect
			//"projectile_trail_effect_0" 					"P_plasma_proj_LG_amp"// Amped EPG trail
			//"projectile_trail_effect_0" 					"P_plasma_proj_LG_DLight"// EPG trail
			//"projectile_trail_effect_0" 					"P_doubletake_proj"// Doubletake pojectile trail
			//"projectile_trail_effect_0" 					"P_doubletake_proj_burn"//Amped Doubletake pojectile trail
			//"projectile_trail_effect_0" 					"P_dragonsbreath_trail"// Scorc pojectile trail
			//"projectile_trail_effect_0" 					"wpn_grenade_frag_softball_burn"// Softball smoke trail
			"projectile_trail_effect_0" 					"weapon_40mm_projectile"// 40mm trail effect
			//"projectile_trail_effect_0" 					"P_projectile_lstar"// L-Star projectile trail
			//"projectile_trail_effect_0" 					"P_plasma_proj_MD"// Cold War projectile trail 
			//"projectile_trail_effect_0" 					"P_plasma_proj_MD_amp"//Amped Cold War projectile trail 
			//"projectile_trail_effect_0" 					"P_wpn_arcball_trail"// Thunderbolt projectile trail 
			//"projectile_trail_effect_0" 					"P_wpn_arcball_trail_amp"// Amped Thunderbolt projectile trail
			//"projectile_trail_effect_0" 					"Rocket_Smoke_Large"//Smoke from Rocket Launcher

![KraberProjectile](https://user-images.githubusercontent.com/37307454/152890210-8151946d-7f54-4f8e-b816-cf69c1742c08.gif)
![EPGProjectile](https://user-images.githubusercontent.com/37307454/152889960-f4d566d5-fab4-4017-9406-0388b90e8730.gif)
![ColdWarProjectile](https://user-images.githubusercontent.com/37307454/152889862-6d621a6c-c44f-43a1-9e66-da2d9fe07fd7.gif)

## Changing Scope version for Snipers
 Scrolling just a little from the start when we open one of the type of sniper files `mp_dmr_fov, mp_doubletake_fov, mp_kraber_fov`
 We can find those values that showed bellow

			//"bodygroup_ads_scope_set"	"1" //set look of the scope while ads 

			//1 - Threat scope 
			//2 - Scope with zoom but for that one you need to set value of "ui7_enable" to "1" so holo will work
			//3 - Default sniper scope

	"ui7_enable"		"0" //holo for scope 2
	UiData7
	{
		"ui"							"ui/variable_zoom_crosshair"
		"mesh"						"models/weapons/attachments/attach_scope_ads_2_crosshair"
		Args
		{
			vis							player_zoomfrac
			ammo						weapon_ammo
			clipSize					weapon_clipSize
			clipCount					weapon_stockpileClipCount
		}
	}

To change visual look of the scope we wantm we need to change this value and `decomment "//"` it 
			//"bodygroup_ads_scope_set"	"1" //set look of the scope while ads 
Here explainted what value changing on what type of the scope
			//1 - Threat scope 
			//2 - Scope with zoom but for that one you need to set value of "ui7_enable" to "1" so holo will work
			//3 - Default sniper scope
For Variable Zoom `that have value of 2` we need additionally activate `"ui7_enable"` - holohraphic part of the Variable Zoom that can be activatet separatly from Variable Zoom

	"ui7_enable"		"1" //holo for scope 2
	UiData7
	{
		"ui"							"ui/variable_zoom_crosshair"
		"mesh"						"models/weapons/attachments/attach_scope_ads_2_crosshair"
		Args
		{
			vis							player_zoomfrac
			ammo						weapon_ammo
			clipSize					weapon_clipSize
			clipCount					weapon_stockpileClipCount
		}
	}

![Variable Zoom Visual](https://user-images.githubusercontent.com/37307454/152889465-2fca9bfe-c45e-4328-9ebb-afe889e5dd9f.gif)

			"bodygroup_ads_scope_set"	"1"

![Threat scope ](https://user-images.githubusercontent.com/37307454/152889578-b335ad7d-55bc-475d-81e7-6cf9342c166c.gif)

Want to ask me something? feel free to dm in my discord: Avalar#2742

v1.0 - Adding Custom FOV and FOV Viewmodel for scopes
- Several presets for Hipfire model
- Custom projectile trails can be modified for Kraber, Wingman Elite, Doubletake and other projectile weapons in mp_kraber_fov mp_doubletake_fov mp_shotguns_fov mp_defender_fov mp_wingman_e mp_rockets_fov
- Default scope can be changed for Kraber DMR and Doubletake in mp_kraber_fov mp_dmr_fov mp_doubletake_fov 

Go into CustomScopeFOV\mod\scripts\weapons where all files stored and you can modifiy

v1.0.1 
- Fixed compatability problems with Thinderstore
- Updated Readme
- Added projectile trail effects for `mp_defender_fov.txt` it stored every weapon with projectile
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Notes: Northstar requires to making this mod work: https://github.com/R2Northstar/Northstar
     
Install mod by going to Titanfall 2 root directory >>> "R2Northstar" and drop mod folder named "CustomScopeFOV" into "mods" folder.
