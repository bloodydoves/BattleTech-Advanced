BT Advanced Starters Custom

So you want to make your own start! Here's how to do so. 

Why would someone want to do this??
- You want to neatly organize your starter options in a mod pak.
- You wished you'd start with different mechs, but don't want to mess with core files.

How to make your own custom starter:

1. Make a copy of an existing start from BT Advanced Starters/BTA_Starters_Base.
2. Change line  8 to give it a unique ID (this is required for clean loading in-game).
3. Change line  9 to give it a unique name (this is the name in the menu in-game).
4. Change line 12 to update the career score modifier (larger numbers indicate harder starts).
5. Change line 17 to the planet you'd like to start on (this goes by planet name as indicated inside of the planetdef that defines the planet; you can find BTA's planetdefs in InnerSphereMap/StarSystems).
6. Change line 22 to pick what lists it will randomize starting mechs from.
	- Every entry (comma seperated) is csv with a Collection of any number of Mechs. Every entry will randomize you one mech from the list. You can use the same list multiple times.
	- Do not have less than 1 or more than 6 entries that add the same type of unit (i.e. more than 6 lists of mechs or 6 lists of tanks). You *can* have more than 6 total lists, as long as they provide different types of units (mechs, vehicles, battle armor).
	- Do not use spaces.
	- You can add your own lists in the BTA_itemCollection_Mechs folder, do not use spaces in their name. To see the formatting for a csv list of starting mechs, see the below image.

7. Start BTA and select New Career; Select under "Starting Planet and Mechs".