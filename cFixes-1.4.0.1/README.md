# cFixes - Community fixes to HBS BATTLETECH
Bugs fixed as reported here:
https://forum.paradoxplaza.com/forum/index.php?threads/simple-json-typo-fixes-for-1-3.1126334/

These files are the result of the combined work of several community modders, namely:

- Amechwarrior, Hawaii, bug tracing and code review.
- Dr. Banzai, Germany, bug fixing and configuration management.
- scJazz, US East Coast, bug fixes and code review.
- JustinKaseToo, US East Coast (living on West Coast time according to his wife), bug and formatting fixes.
- Sheepy, bug fixes and code review.

Credits:

Special thanks to Ark Evensong for providing the fixes to various pilots and ShadowStalker88 for providing the fix to CRB-27 head hardpoints.

The authors do not claim any intellectual or legal property on the content of these files. 
They are intended for free use and re-use.

### Instructions:
    Copy cFixes folder in to Mods folder created for ModTek.
    
### ModTek/BTML
This mod needs ModTek to work:

https://github.com/BattletechModders/ModTek/releases

Thanks to mpstark and the entire ModTek team for making this mod possible!


## List of Fixes
(by directory)

### StreamingAssets/data/chassis/
    chassisdef_atlas_AS7-D.json - reduced CenterTorso internal structure to 155, max CT armor to match
    chassisdef_atlas_AS7-D-HT.json - reduced CenterTorso internal structure to 155, max CT armor to match
    chassisdef_blackknight_BL-6-KNT.json - fixed variant name to BK-7-KNT
    chassisdef_blackknight_BL-6b-KNT.json - fixed reference to BK-7-KNT
    chassisdef_commando_COM-1B.json - fixed typo: "IB" changed to "1B"
    chassisdef_crab_CRB-27.json - fixed variant name to CRB-20
    chassisdef_griffin_GRF-4N.json - fixed variant name to GRF-2N
    chassisdef_thunderbolt_TDR-5S.json - fixed typo: "well armored and" changed to "well armed and"
    chassisdef_trebuchet_TBT-5N.json - fixed value: CT max Armor 120 changed to 160
    chassisdef_zeus_ZEU-6S.json - fixed value: Jump Jets 3 changed to 4

### StreamingAssets/data/constants/
    CombatGameConstants.json - 7th Evasion Pip fixes AI ASSERT lock from Sure Footed+10Piloting unit moves for 6Pips

### StreamingAssets/data/contracts/
All Escort and Capture Base contracts have had the word "Dropship" replaced with "DropShip" as used in the BT writers guide.

    DefendBase_Bodyguards.json - removed redundant "the" in dialogs
    FireMission_DataLiberation.json - Typos and missing Faction Tag Calls
    FireMission_DataLiberation_Hard.json - Typos and missing Faction Tag Calls
    Story_5_ServedCold_Default.json - Missing space between "Newgrange" and "is"
    Story_5_ServedCold_Template.json - Missing space between "Newgrange" and "is"

### StreamingAssets/descriptions/Lore/
    LoreGreatHouses.json - Ordered Houses "Around the Sphere"
    LoreSuccessorState.json - Ordered Houses "Around the Sphere"
    
### StreamingAssets/descriptions/MechWarriorData/
    TypeMechWarriorBrawler.json - Sure Footing description added
    TypeMechWarriorDefenderAdvanced.json - Sure Footing description added
    TypeMechWarriorFlanker.json - Sure Footing description added
    TypeMechWarriorGladiator.json - Sure Footing description added
    TypeMechWarriorOutrider.json - Sure Footing description added
    TypeMechWarriorPilot.json - Sure Footing description added
    TypeMechWarriorPilotAdvanced.json - Sure Footing description added
    TypeMechWarriorRecon.json - Sure Footing description added
    TypeMechWarriorScout.json - Sure Footing description added
    TypeMechWarriorSentinel.json - Sure Footing description added
    TypeMechWarriorSkirmisher.json - Sure Footing description added
    TypeMechWarriorStriker.json - Sure Footing description added
    TypeMechWarriorTacticianAdvanced.json - Sure Footing description added
    TypeMechWarriorVanguard.json - Sure Footing description added

### StreamingAssets/data/events/
    event_mw_arcadeMercenaries.json - fixed typo: "his" changed to "{TGT_MW.Gender?Male:his|Female:her|NonBinary:their}"
    event_mw_librarySelfImprovement.json - fixed typo: "his" changed to "{TGT_MW.Gender?Male:his|Female:her|NonBinary:their}"
    event_mw_triage.json - missing commas

### StreamingAssets/data/factions/
    faction_MagistracyOfCanopus.json - fixed typo: "conservation" changed to "compensation"
    
### StreamingAssets/data/hardpoints/
    hardpointdatadef_crab.json - fixed head hardpoints
    
### StreamingAssets/data/heatsinks/
    Gear_HeatSink_Generic_Bulk-Bank.json - fixed [AMT] value in StatusEffect Description Details
    Gear_HeatSink_Generic_Improved-Bank.json - fixed [AMT] value in StatusEffect Description Details
    Gear_HeatSink_Generic_Standard-Bank.json - fixed [AMT] value in StatusEffect Description Details
    Gear_HeatSink_Generic_Thermal-Exchanger-I.json - fixed [AMT] value in StatusEffect Description Details
    Gear_HeatSink_Generic_Thermal-Exchanger-II.json - fixed [AMT] value in StatusEffect Description Details
    Gear_HeatSink_Generic_Thermal-Exchanger-III.json - fixed [AMT] value in StatusEffect Description Details

### StreamingAssets/data/mech/
    mechdef_atlas_AS7-D.json - reduced CenterTorso internal structure to 155, moved ammo from Legs to RT
    mechdef_atlas_AS7-D-HT.json - reduced CenterTorso internal structure to 155
    mechdef_blackknight_BL-6-KNT.json - fixed variant name to BK-7-KNT, fixed PPC in wrong HardpointSlot
    mechdef_blackknight_BL-6b-KNT.json - fixed reference to BK-7-KNT, moved DHS from illegal Leg slots to torsos and arms
    mechdef_cataphract_CTF-1X.json - removed tag: "unit_jumpOK", 
    mechdef_catapult_CPLT-C1.json - added tag: "unit_jumpOK", - added tag: "unit_indirectFire",
    mechdef_centurion_CN9-AL.json - added tag: "unit_indirectFire",
    mechdef_commando_COM-1B.json - fixed typo: "IB" changed to "1B"
    mechdef_crab_CRB-27.json - fixed variant name to CRB-20, given Role - Brawler and Lance - Tank tags
    mechdef_cyclops_CP-10-Q - given Role - Sniper and Lance - Support tags
    mechdef_cyclops_CP-10-Z - given Role - Sniper and Lance - Support tags
    mechdef_griffin_GRF-4N.json - fixed variant name to GRF-2N, JJ from Leg to Torso, moved DHS from illegal Leg slots to torsos to match "Greed"
    mechdef_griffin_GRF-4N_fp_greed.json - fixed variant name to GRF-2N, JJ from Leg to Torso
    mechdef_hatchetman_HCT-3F - given Lance - Assassin tag
    mechdef_highlander_HGN-732b.json - Adjusted Torso Front Armor to match Record Sheets
    mechdef_highlander_HGN-733.json - Adjusted Center Torso Front Armor to match Record Sheets, allocated "spare" armor point to CTR
    mechdef_highlander_HGN-733P.json - added tag: "unit_indirectFire", adjusted Torso Front Armor and HS+ammo locations to match Record Sheets
    mechdef_jagermech_JM6-A.json - added tag: "unit_indirectFire",
    mechdef_orion_ON1-K.json - added tag: "unit_indirectFire",
    mechdef_quickdraw_QKD-5A.json - removed tag: "unit_indirectFire",
    mechdef_zeus_ZEU-6S.json - added tag: "unit_indirectFire",

### StreamingAssets/data/movement/
    movedef_crab_CRB-27 - Fixed Walk and Sprint distances.  From 120/200 to 140/240

### StreamingAssets/data/pilot/
All pilot files have been refactored to stock passive traits, this is over 90+ files and summerized here for brevity.  Any missing passive traits have been added to conform to the standard progressions.  Story pilots with more than the normal amount of abilities have been retained, but their passive traits have been brought up to standard.  Turret "pilots" have not been touched.
    
    Pilot Edits Other Than Passive Traits
    
    pilot_backer_Brown - Typo in bio "ambivalence" corrected to "ambivalent."

### StreamingAssets/data/simGameConstants
    SimGameConstants.json - Various extra commas, missing comma after "uixSvgIcon_contract_Travel"

### StreamingAssets/data/starsystem/
    starsystemdef_Camadeirre.json - fixed typo: "Camadeirre" change to "Camadeierre"
    starsystemdef_MacLeodsLand.json - fixed typo: "Concordant" changed to "Concordat"
    starsystemdef_NewGanymede.json - fixed typo: "Concordant" changed to "Concordat"
    starsystemdef_NewVandenburg.json - fixed typo: "Concordant" changed to "Concordat"
    starsystemdef_Renfield.json - fixed typo: "Concordant" changed to "Concordat"
    starsystemdef_Samantha.json - fixed typo: "Concordant" changed to "Concordat"
    starsystemdef_Taurus.json - fixed typo: "Concordant" changed to "Concordat"
	
### StreamingAssets/data/upgrades/cockpitMods/
	Gear_Cockpit_StarCorps_Dalban.json = fixed typo: "Morale" changed to "Resolve"

### StreamingAssets/data/vehicle/
    vehicledef_BULLDOG.json - added Front MG and ammo
    vehicledef_DEMOLISHER.json - added missing 4th ton of AC/20 ammo
    vehicledef_MOBILEHQ_ARMORED.json - Fixed armor to match TT values
    vehicledef_SCORPION.json - moved MG from Turret to Front
    vehicledef_STRIKER.json - fixed value: Turret Armor 120 changed to 110
    vehicledef_SWIFTWIND_ARMORED.json - fixed tonnage and armor to match possible TT config

### StreamingAssets/data/vehicleChassis/
    vehiclechassisdef_MANTICORE.json - Fixed armor and internals
    vehiclechassisdef_SCORPION - moved AP hardpoint from Turret to Front
    vehiclechassisdef_STRIKER.json - Fixed armor and internals
    vehiclechassisdef_SWIFTWIND.json - Fixed armor and internals
    vehiclechassisdef_SWIFTWIND_ARMORED.json - Fixed Tonnage and armor and internals

### StreamingAssets/data/weapon/
    Weapon_Gauss_Gauss_1-M7.json - added weapon bonus description
    Weapon_Gauss_Gauss_2-M9.json - added weapon bonus description
    Weapon_LRM_LRM5_2-Delta.json - fixed value: "Instability" : 5, changed to "Instability" : 4,
    Weapon_LRM_LRM10_2-Delta.json - fixed value: "Instability" : 5, changed to "Instability" : 4,
    Weapon_LRM_LRM15_2-Delta.json - fixed value: "Instability" : 5, changed to "Instability" : 4,
    Weapon_Laser_LargeLaserER_1-Blankenburg25.json - added weapon bonus description
    Weapon_Laser_LargeLaserER_2-BlazeFire.json - added weapon bonus description
    Weapon_Laser_LargeLaserPulse_1-Thunderbolt12.json - added weapon bonus description
    Weapon_Laser_LargeLaserPulse_2-Exostar.json - added weapon bonus description
    Weapon_Laser_MediumLaserER_1-MagnaVI.json - added weapon bonus description
    Weapon_Laser_MediumLaserER_2-BrightBloom.json - added weapon bonus description
    Weapon_Laser_MediumLaserPulse_1-RakerIV.json - added weapon bonus description
    Weapon_Laser_MediumLaserPulse_2-Magna400P.json - added weapon bonus description
    Weapon_Laser_SmallLaserER_1-Diverse_Optics.json - added weapon bonus description
    Weapon_Laser_SmallLaserER_2-BlazeFire.json - added weapon bonus description
    Weapon_Laser_SmallLaserPulse_1-Maxell.json - added weapon bonus description
    Weapon_Laser_SmallLaserPulse_2-Magna200P.json - added weapon bonus description
    Weapon_PPC_PPCER_0-STOCK.json - added general PPC status debuff "sensors impaired"
    Weapon_PPC_PPCER_1-MagnaFirestar.json - added general PPC status debuff "sensors impaired"
    Weapon_PPC_PPCER_1-MagnaFirestar.json - added weapon bonus description
    Weapon_PPC_PPCER_2-TiegartMagnum.json - added general PPC status debuff "sensors impaired"
    Weapon_PPC_PPCER_2-TiegartMagnum.json - added weapon bonus description
