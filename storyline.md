
# Storyline



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


### 'Looks like loot's back on the menu' Quest
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
- positive: normal scavs are not hostile, maybe they can also have santa AI sometimes
- negative: passive income from your gang, start raid with follower(s) like a boss TBD

## Scav Ally Quest Chain

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


*player completes intro quest*

- default_scav_faction is now friendly with player_faction

- fence/scav_rep_vendor unlocks quests for taking zones from bosses.

formulaic faction missions spec: 

- faction_intro_quest - get info on boss: from other trader[via fetch/kill quest], from looting a quest item off a mob.

- take_zone_from_boss_quest - go to position and hold for x minutes. [scripted waves will spawn there]

    - success changes bots generated in that zone to no longer be 100% boss_faction_follower

    - could be multiple of these, and maybe optional

- killing sub-boss quest - replaces a normal boss like the intro quest, but no special conditions - gear restrictions etc.

- defeating boss quest - final boss encounter - wave defense or just a tough boss encounter, etc.

    - disables all spawning of the boss and his followers.

    - enables a repeatable quest for spawning the boss: "flashback/remembering *boss_name*"

### TODO more non-formulaic quests [Scav Ally Quest Chain]

## Scav Enemy Quest Chain

### 'These are our streets' Quest [Scav Enemy Quest Chain]
``` quest_text
Dude, your a fucking menace and word is getting around. The locals have started to call you Ubiyt.

Might as well embrace your newfound reputation huh? 

Maybe you can assemble a crew of your own and take on the other bosses. 
To get some followers you'll need to prove you can waste more than just the local wildlife, 
becauase - let's face it - no ones trusts you enough to take point anymore.

Survive a real challenge and prove you can pointman and I'm sure folks will start taking you seriously.
```

### TODO more [Scav Enemy Quest Chain]

generally missions would be the same as the ally route: dismantle each crime bosses faction

intro mission is to prove yourself, extract labs, extract reserve via d2, fetch quest, kill quest with conditions, something like that.

followed by a wave defense to establish your 'base' at customs [fortress?]
  - unlocks first follower [maybe they spawn with you/maybe they spawn at the base]

lead into formulaic faction missions


### TODO more non-formulaic quests [Scav Enemy Quest Chain]


