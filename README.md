
# Tarkov Factions Expanded Mod (TFE)


Essentially this mod overrides the spawn configs of locations and bot generation during a raid 
if certain conditions are met in order to create consistent map-scenarios, like for story quests.

Then uses this to create a storyline around the factions of Tarkov to make the world 
dynamic/reactive to player involvement.

Mod is intended to be used with [Single-Player-Overhaul](https://github.com/kobrakon/SPO_DEV) 
& Path-to-Tarkov but could also support standalone.

### Checkout the current [storyline spec here](storyline.md)

## Mod Specification Stuff 
some of this has been proven/POCd by piggybacking Lua's SpawnRework and Fin's AI BotGeneration:
-	faction(ai_role) alliances
- made usec and bears separate roles.
-  made default scavs (assault) friendly to one pmc role.
    - other scav roles (*follower, raiders,etc) were still hostile

Things I know are possible via other mods:
- custom quest framework (Andruis)
- custom bot loadouts (Fin)
- spawn config and some custom spawn points (Lua)
- Audio replacement in the client (Fox's .dlls), to add [custom boss_faction_follower voicelines](Voicelines_script.md)

Core aspects which need work:
- Conditional Map-Scenario Framework:

  a conditions processor based on json spec files for validating abstract conditions against the game/player state
  - when used with bot generation
    - full-replacement or merging of bot inventories
    - full-replacement or merging of bot behaviors
  - when used with map/spawn generation
    - full-replacement or merging of spawn wave properties
      - zone,time/wave,bot_types_quantities


Unproven aspects:
- getting bots to follow player at raid start.
- adding/modifying bot voices
- placing loot in specific containers at raid start
- TBD


### Quest type examples

- Assassinate a Boss - as a scav OR as pmc via disguise/diplomacy/force

- defend/capture a location [reserv_bunker, sawmill, dorms, fortress, woods_town, etc...]

    - insta spawn bots

    - wave defense

    - custom boss wave with specific boss_skin and boss_ai

- TODO more generic quest types

### condition attributes examples

- quest/objective status,

- player equipment entering raid (wearing scav vest, holding item, etc.)

- TBD - player world persistence objective incomplete - power on/off, quest decisions, world event, etc....


###  Scenario/spawn/bot modification attributes examples

- faction loyalty changes - temporary [ally/enemy] faction to player faction - disguise, diplo event, etc...

- bot spawn changes:

    - insta load certain bots[role/faction,quantity,zone,time/wave] - bosses, certain factions etc

    - configuration of waves to spawn_points - defense of point quests, extract campers, etc...

- bot gen changes:

  - spawn with specific quest item(s) for a bot_type/bot_id/zone/etc

  - specific gear worn by bot roles (boss_follower's wearing obvious items, un wearing un-gear, black division wearing all-black gear)


