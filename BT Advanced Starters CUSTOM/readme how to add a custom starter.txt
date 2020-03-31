BT Advanced Starters Custom

Who is this for?
- You want to neatly organize your starter options in a mod pak.
- You wished you'd start with different mechs, but don't want to mess with core files.


How to make your own custom starter:

1. Make a copy of Commandos in the Starters Folder.
2. Change line  9 to give it a unique ID.
3. Change line 10 to give it a descriptive name (used in selection menu).
4. Change line 18 to any planet you'd like to start on.
5. Change line 23 to pick what lists it will randomize starting mechs from.
	- Every entry (comma seperated) is csv with a Collection of any number of Mechs. Every entry will randomize you one mech from the list. You can use the same list multiple times.
	- Do not have use less than 1, or more than 6 entries. Your game will break.
	- Do not uses spaces.
	- You can add your own lists in the USERDEFINE_itemCollection_Mechs folder, do not use spaces in their name.
	- Modpacks tend to have their own itemCollections added you can refer too, or use the ones in the base game files for inspiration (see BATTLETECH\BattleTech_Data\StreamingAssets\data\itemCollections).

6. Use the ModTek Injector.
7. Play BattleTech  > New Career; Select under "Starting Planet and Mechs".