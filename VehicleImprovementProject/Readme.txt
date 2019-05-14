Vehicle Improvement Project
By Cargo_Vroom
twitch.tv/cargo_vroom

----------------------------

Battletech has a lot of really cool tanks and other combat vehicles. 
They are not well represented in the base game.
HBS included very few,in the game, and most of them are unusually weak.
This mod aims to increase variety and make them more interesting and overall increase their tactical importance.

This mod adds many lore-correct combat vehicles to the game. (Stats taken from Solaris Armor Works and Sarna.net).
This includes everything from flimsy little hovertanks to 100 ton Assault vehicles that can challenge any mech.

They all need to use existing graphics because adding new art assets to the game is still pretty experimental.
But I've done my best to make the models chosen suggest what sort of vehicle you're dealing with.

Also, it incorporates vehicle AI improvements based on work by LadyAlecko the co-developer of Roguetek. 
They'll be less eager to get stepped on now, and overall do a better job of providing supporting fire for mechs.

---------------------------------

To Install:


Requires BTML and Modtek!!!

Delete old version before upgrading.

Place the VehicleImprovementProject folder in your Battletech/mods folder.
Consult modtek's instructions if you have trouble.

If you want VIP to take precidence over other mods that change vehicles move it to the end of your modtek load order.

(A version of this mod is included in Roguetech. But it's balanced a little differently.
If you want to use this one for the additional features overwrite the files, then move VIP to the bottom of your load order.)

--------------------------------------

Compatibility:

Other mods that add vehicles may lead to both mod's version of that vehicle appearing.

There may be conflicts with other mods that change global values for vehicles like armor multiplier or AI.
Make sure whichever mod you want to get the last word is closer to the end of the load order.

-----------------------------------

Credits & Thanks:

LadyAlecto for help, and honoring me by including this mod in her fantastic Roguetech project.
All the folks at the BTGame modding discord for the many questions they answered.
ContactWithTheEnemy for encouragement and testing.
Everyone who has watches my Battletech streams.
And of course HBS Studios for making this great game.

----------------------------------

Changelog:

1.0.0

Added Puma assault tank (With lore-appropriate + weapons. Scariest vehicle in the mod probably).
Added Rhino assault class fire support tank.
Added Ontos (LRM)
Added two version of Von Luckner heavy tank.

Dynamic Lances rebalanced to account for increased vehicle lethality, heavier vehicles appear 0.5-1 skull later than before.
Implimented MechResizer to scale the new vehicles properly.

Added Heavy Vehicle Flamer (Contributed by LadyAlecto)
Replaced most vanilla vehicle flamers with the new one. (Happy looting)
All Convoys now contain one tank instead of being all APCs.
Introduced custom unit_hover tag to get more control over when fast units spawn.
Gave all VIP and vanilla vehicles lance role tags.
Added lance defs for Mixed Diff 3.
High difficulty Assasination targets will now sometimes have light hovertank buddies intead of a light mech.

Pathingdef change: tracked vehicles now move as easily backward as forward.
Buffed the generic pilot used in friendly convoy vehicles.
Buffed fallback pilots used if spawner derps. (Something of a general fix)
Removed "Heavy" tag from Turhan APC (Too fragile to spawn in late-game escort missions).
Corrected Striker's structure values.
Corrected Zyphyr armor and redesignated "Zephyr (SRM2)"
Boosted Pegasus sensor range as a standin for BAP.
Gave Patton and Rommel the Defiance brand cannons specified in their fluff.
Gave Scimitar (LRM) a + weapon because it's BV is half what's normal for that bracket.
Vehicle evasion result 0.8 to 0.85 because of minor rounding issue.
    
This version number breaks my conventional incrimentation method, but we're going to have a version that's exactly 1.0 darn it.

0.8.5

Gave Vanilla LRM/SRM Carriers a 'turret' hit location with stats.
    This sidesteps a vanilla bug that causes damage to occasionally be ignored becaue it can roll to hit the non existant turret.
    It was becoming more of a problem as I adjusted hit probabilities and turret hits became more common.
    "Roof" Armor is set to 80% of side armor.
    Note that while this makes total armor go up they aren't tougher.
    It makes it possible for hits that in vanilla would do nothing to cause damage.
Reversed a previous change and gave roofs/turrets to all my Carriers, Hunters and Saladins.
    
Added Patton and Rommel, a pair of relatively swift heavy tanks.
Added Scimitar variant (LRM15)
Added Pegasus variant (trades Mlaser for SRM6)

0.7.9hf

Squashed bug that caused Ontos to have no turret armor.
Changed Ontos model from Demolisher to Carrier.

Version 0.7.9

*Tried to make vehicles even more cautious.
*Vehicle armor multiplier 0.75 -> 0.8,
*Made vehicles inherently 10% harder to hit; reason they are low slung and can go hull down.
*Vehicles now get 20% fewer Evasion pips from movement to compensate because they are not as agile as mechs.
*Spawning Balance changes:
	Tagged Bulldogs as "Medium" vehicles instead of heavy.
	Tagged Hunter B as "Medium" instead of light because they were murdering my light mechs in testing.
	Tagged Demolisher-D as "Heavy" because it's fragile.
	Added "Assault" tag to Brutus-B.
	Added "Heavy" tag to Myrmidon
    Cloned the vanilla Manticore to make it spawn more often.
*Corrected Shrek-AC armor and MG mount locations.
*Removed "Turret" hit location from vehicles that shouldn't have one: Saladin, Hunter
*Removed all individual movedefs, replaced with generic ones for the handful of different speed categories.
*Gave minor equipment upgrades to a few units that are noticably weaker relative to category:
	Ignis (Both), Vedette (Both), Saladin (most fragile one), Po Heavy Tank.
*Gave Pike the advanced fire control system the fluff says it's supposed to have.
*Changed Marsden model from scorpion to bulldog.
*Changed Myrmidon model from scorption to manticore.
*Changed Harasser model from sldfdrone to striker.
*Changed Brutus-C model from demolisher to schrek.
*Added missing "unit_release" tags that may have caused certain units to not spawn reliably.
*Added same tag to 5 vanilla vehicles that were also missing it, just in case.
*Tweaked vehicle section hit chances, now easier for shots to land on turrets.
*Made it possible, but rare, to hit a vehicle's rear from side arc.
*Took control of the "ToHitSelfWalkVehicle" setting.
*Moved Light turrets to phase 3, medium to phase 4

*Added Axel heavy tank (AC/20, 2 versions)
*Added Scimitar light hovertank. (AC/5, SRM4)
*Added Pegasus scout hovertank. (Mlas, SRM12)
*Added Tiger T-12 medium tank. (AC/10, SRM4, 3 MG)
*Added Laser Carrier. (8 Mlasers on a truck)
*Added Sabaku Kaze. (top tier laser hovertank)
*Added Ontos heavy tank. (Big boy laser carrier)
*Added Maxim Transport (Missiles and MGs)
*Added Scorpion variant. (Mlasers)
*Added Hunter variant. (LRM15+MGs)
*Added Vedette variant. (AC/2)
*Added Harasser-F (Flamers)

Version 0.2.9hf

*Fixed infinite loading bug caused by Flamer Behemoth. (Thanks LadyA)

Version 0.2.9:

Added Behemoth (Flamers)
Added Brutus (PPC #2)
Added Hunter (LRM10)
Added Ignis (SRM)
Added Light LRM Carrier
Added Saladin (Base Model)
Adjusted Turret Abilities
Fixed Schrek AC overwriting the PPC version.
Corrected Hunter armor values.
Uniquified def names; Improved compatibilty with other mods that add units.

Version: 0.1.1 (First Release)

Added:

APC Turhan,
Behemoth,
Behemoth Up-Armor,
Brutus,
Brutus PPC,
Bulldog AC,
AC/2 Carrier,
Heavy LRM Carrier,
Demolisher Defencive,
Drillson,
Harasser,
Hunter,
Ignis,
Light SRM Carrier,
Marsden II,
Marsden IIA,
Myrmidon,
Pike,
Po heavy Tank,
Saladin Up-Armored,
Schrek AC
Vedette,
Zephyr,
Zhukov

Implimented improved vehicle behavior variables from Roguetech 0.9859
Adjusted vehicle base initiative and to-hit values.
Vanilla Bulldog given the machine gun it's supposed to have,
Vanilla Wheeled APC turret armor corrected from 210 to 50,
Vanilla Bulldog, Striker, Vargr given correct tonnage class,
Vanilla Bulldog, Striker, Sleipnnir, Vargr given correct pathingdef.