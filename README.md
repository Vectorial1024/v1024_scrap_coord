# Scrap Delivery Coordination
When delivering scrap, Manticores spread out to use all processors if possible.

- Nexus Mods: https://www.nexusmods.com/x4foundations/mods/1234
- Steam Workshop: https://steamcommunity.com/sharedfiles/filedetails/?id=3044228579

## Quick info
This mod is directly inspired by [Multi Scrap Processor Station Fix](https://www.nexusmods.com/x4foundations/mods/882). At one point, I was a user of that mod, but then I still notice some scrap processors running empty when there are multiple Manticores with scrap waiting nearby.

Basically, vanilla scrap processing flow looks like this:
1. Pick up scrap cube (or sth)
2. Move into the zone of the destination
3. Pick a random processor
4. Move closer
5. Try to drop the scrap cube (it does not know whether the processor is usable)

By analyzing vanilla code, I noticed there is a chance where multiple Manticores will pick the same processor, which is likely the main reason why Manticores are often seen "not delivering scrap cubes": they simply arrived at the same processor, notice that it is in use, and just stop and wait.

This mod simply spreads out the Manticores when they are approaching the processors. When a Manticore has selected a certain processor, in the upcoming 5 minutes or so, other Manticores will avoid selecting the same processor if possible.

Because we currently cannot know whether specific processors are usable, this mod is not perfect. But still, you will see that your scrap processors are running at a higher load.
