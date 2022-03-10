Rarity Tied Spawner (RTS) is a mod for HBS's Battletech computer game. It is a small, focused mod with a single purpose - adjusting the rarity of units based on their tags.

## `moreCommonTags`
In settings.json, `moreCommonTags` is a dictionary of tags, mapping each to an integer.

When the game spawns random units for a lance, it makes a list of all units that match the lance's tags. For each unit, RTS then calculates a `toAdd` value based on its tags, and pushes that many copies of the unit onto the list.

Think of it as a bunch of raffle tickets in a hat. If a unit matches a tag in `moreCommonTags`, then RTS puts additional copies of that unit into the hat the game pulls from. Simple.

`toAdd` can be negative in the configuration, but the total can never go below 0. `"unit_never_spawn": -1000` will not remove the initial copy of a unit from the list, but it will counteract any other `moreCommonTags` the unit might also have.
