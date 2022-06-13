
# Tarkov Factions Expanded Mod (TFE)


Essentially this mod overrides the spawn configs of locations and bot generation during a raid if certain conditions are met in order to create consistent map-scenarios, like for story quests.

some of this has been proven/POCd by piggybacking Lua's SpawnRework and Fin's AI BotGeneration:
--	faction (role) alliances
- made usec and bears separate roles.
-  made defualt scavs (assualt) friendly to one pmc role.
    - other scav roles (*follower, raiders,etc) were still hostile

Things I know are possible via other mods:
- custom quest framework (Andruis)
- custom bot loadouts (Fin)
- spawn config and some custom spawn points (Lua)
- Audio replacement in the client (Fox's .dlls), to add [custom boss_faction_follower voicelines](Voicelines_script.md)

Core aspects which need work:
- Conditional Map-Scenario Framework:
  condition processor for scenario selection/execution based on scenario spec files
  full-replacement/merging of spawn wave properties based on the spec file
  full-replacement/merging of bot inventories based on the spec file
  full-replacement/merging of bot behaviors based on the spec file

Unproven aspects:
- getting bots to follow player at raid start.
- modifying/adding bot voices
- TODO


Quest examples:

- Assassinate a Boss - as a scav OR as pmc via disguise/diplo/force,

- Capture a location [reserv_bunker, sawmill, dorms, fortress, woods_town, etc...]

    - insta spawn bots

    - wave defense

    - custom boss wave with specific boss_skin and boss_ai



Scenario/spawn/bot condition attributes:

- quest active/quest objective incomplete,

- player world persistance objective incomplete - power on/off, quest decisions, world event, etc....

- quest objective incomplete,

- ?specific gear worn by pmc?


Scenario/spawn/bot modification attributes:

- faction loyalty changes - temporary [ally/enemy] faction to player faction - disguise, diplo event, etc...

- bot spawn changes:

    - insta load certain bots[role/faction,quantity,zone,time/wave] - bosses, certain factions etc

    - configuration of waves to spawn_points - defense of point quests, extract campers, etc...

-	bot loot changes:

-	drop specific quest item(s) from a bot/zone



# Storyline Ideas



The collapse of the state at the end of the Contract Wars left a power vacuum in Tarkov. The local bosses, as well as outside powers, are now vying for control of zones within the region. Will you escape from Tarkov, or will you succumb to that same lust for power?

The story centers around two main paths. The players escape, and the faction dynamics within the zone.

Escape quests are the usual EFT missions and a few more to create the full narrative until BSG gets theirs together.

Faction quests are the core focus. Player reputation and quest progression will modify:
- factions aggression to the player and each-other
- boss spawns, when and where
- boss_factions can persistently/randomly control spawnpoints in maps [dorms/sawmill/cottages]
- hopefully new boss follower voicelines for better identification of factions
-


### Background

Starting at the end of the contract Wars all pmc faction members are stranded in the zone.

Lore: Tactical Nukes and emp strikes in the area have knocked out all current outside connections and communications. Maybe a broader war is also now going on TBD.

While the war is over, Pmc faction members still hold their old allegiances.

There is very little civilian activity across the region, and crime bosses have yet to establish themselves.


### 'Intro' Quest
``` quest_text

Well... it looks like they fucking left us here! I don't know who thought it was a good idea to shoot of all those missiles... but i can't get anyone on comms.

Our contract may be over, but I still don't trust those [USEC/BEAR] fucks. Still, it seems like were stranded here with'em though until things at the border-zones cool off.

There are still a few folks around willing to cut a deal, but they'll probably want some favors done in return.

Maybe one of them knows how we can get out of here.

```

*player early leveling scales enemy quantity and avg difficulty*

*player progresses through introductory quests, triggers civilians return to tarkov [more scavs, no bosses]*


### 'Looks like loots back on the menu' Quest
``` quest_text

It seems like more people are starting to explore the warzone. 

Yea this was inevitable, but I wonder how fucked up it must be out there for them to want to come here. 

Anyway, this is bound to cause some trouble.

```

*player progresses through main questline, triggers crime factions in tarkov [enables boss factions(boss_role&1_boss_follower_role)]*

### 'Who runs the streets' Quest

``` quest_text

Well, can't say I didn't see this coming, but the locals are starting to setup shop here in the zone. 

I heard names floating around while scav'ing at the mall: Reshala, Sanitar... and uh... watch out for Killa, dudes nuts.

Some guys mentioned Reshala setting up shop in the old dorms out by the factory. 

I would have asked for more but Killa started popping off with his RPK so we got the hell out of there.

```

*player reaches scav_faction loyalty threshold through quests/gameplay, this unlocks a tarkov_factions questline [faction_changes, boss_quests/changes]*

Positive Scav Rep leads to a Scav Alliance quest chain where the players faction defeats the bosses and brings an end to scav on scav violence in the zone.
Negative Scav Rep leads to a Scav Domination quest-chain where the players becomes a Tarkov boss trying to defeat the other bosses.

key differences:
positive: scavs are not hostile
negative: passive income from gang, start with follower(s) in raid


### 'Taking back Tarkov' Quest [Scav Ally Quest Chain]
``` quest_text

You've been making quite the name for yourself among the locals.

Some of them are fed up with how Reshala's been running things at the customs checkpoint and want a change in leadership, but not everyone's so ready.

Word is he leaves his little brother running things while he's hitting the lab.

How about we stir some shit up. If we can start drama between reshala and the other locals, maybe they'll be willing to align themselves with us.

Dress up as a local and go kill Reshala's brother when he's around. That will really give Reshala something to be mad about...

```
- TLDR: Assassinate Reshala's little brother at the dorms - as a scav, or as pmc while wearing a scav vest, balaclava, and ushanka hat. other scavs will not interfere.
- Reshala's brother [Shturman skin, no guards, replaces reshala spawn %75 chance, ai_easy, behavior: reshala?]


*player completes tarkov_reclaimation intro quest*


-- default_scav_faction are now friendly with player_faction

-- fence/scav_rep_vendor unlocks quests for taking zones from bosses.

- faction_intro_quest? - get info on boss: from other trader[via fetch/kill quest], from looting a quest item off a mob.

- take_zone_from_boss_quest - go to position and hold for x minutes. [scripted waves will spawn there]

    - success changes bots generated in that zone to no longer be 100% boss_faction_follower

    - could be multiple of these, and maybe optional

- killing sub-boss quest? - replaces a normal boss like the intro quest, but no gear restrictions etc.

- defeating boss quest - final boss encounter is wave defense or just a tough boss encounter, etc.

    - disables all spawning of the boss and his followers.

    - enables repeatable quest for triggering respawning of the boss: "flashback/remembering the glory days etc."