# What is Postal 3 Angel?

[Postal 3 Angel](https://www.moddb.com/mods/postal-3-angel) is a mod released by **WhackJob Interactive** for Postal 3 which fixes several bugs but it's main point is adding the [AngelScript scripting language](https://whackjobint.github.io/angelscript/).

Developed for [Catharsis Reborn](https://www.moddb.com/mods/catharsis-reborn) exclusively, but it was backported for Postal 3.

!!! note Note
	The mod is heavily focused on extending AngelScript, as such there will not be any further improvements from Catharsis Reborn.

## Features/Fixes

- Completely DRM-free, can be used with any copy of Postal III
- Implemented AngelScript from Catharsis Reborn (server-side only), with serialization support enabled by default (Over 250+ functions, and 10+ object types!)
- Postal3Script fixes/additions
- New console commands, all of them start with the `wj_` prefix
- Fixed buggy `InputFireFSMScriptEvent` fire input interaction with triggers, this might cause side effects with missions (since mappers used triggers with this bug)
- NPCs will now ignore locked nav meshes in their pathfinding (When not in combat only, does not affect vanilla missions, maps have to be edited)
- Fixed grab controller sometimes crashing the game (When using shopvac)
- Fixed game sometimes crashing when throwing a grenade (weapon)
- Fixed weapon damage values not being correctly read by NPCs (NPCs with weapons only dealt 1 damage to the Player)
- Fixed screen staying tilted sometimes when taking fall damage
- Fixed throwing any kind of item crashing the game (ballistic controller)
- Added `wj_trigger_angelscript` trigger, calls AngelScript when touched
- Added `wj_logic_angelscript` logic entity, calls AngelScript via input function (Global only)
- Fixed NPCs not playing Deploy sound for weapons
- NPCs (Humans only) can now pick up weapons off the ground if it's scripted
- Fixed Human NPCs being unable to pick up anything after level transition
- Fixed Gasoline particles and sounds breaking after level transition or save loading
- Fixed Gasoline primary fire holster/deploy bugs
- Fixed Weemote breaking after level transition or save loading
- Fixed Weemote burst piss bug while holstering
- Fixed Weemote having no *piss* after transition or save/load
- Fixed M16 having no fire sound while a cat was attached
- Fixed dead NPCs' speech not stopping
- Hint nodes are now locked when NPCs start using them, they must be freed by either killing, ragdolling, or knocking the NPCs out, or by manually unlocking them in Postal3Script (this is to prevent a crowd using the same node)
- Better and much more detailed Postal3Script crash logs
- Fixed infinite loading loop sometimes when Shopvac had sucked items on transition
- Fixed Human shield crash
- You can no longer arrest/take hostage if the target NPC is on fire
- Hostages/Arrested NPCs are now extinguished if they are on fire on initial action (just in case..)
- Fixed HUD not appearing if the level was changing while arresting
- Players and their Segways now respect Landmark's angle when on transition
- Fixed garbage use targeting (+Now items will actually glow where your crosshair is much more precisely)
- Several P3 console commands that were not protected by `sv_cheats` are now protected (like `giveammo`)
- Fixed Fireaxe and Hammer crashing the game when hitting an NPC that is playing death animation
- Nailbat now deattaches much faster if the NPC was killed
- Fixed picking up buggy shot spit (from Shopvac) crashing the game
- Fixed broken screens by re-enabling `func_monitor` (ex. on PornWorld there were a couple of monitors that didn't work)
- Added `wj_point_viewcontrol` point entity, the P3 version of `point_viewcontrol` (cutscene camera no longer crashes when modders use it)
- Fixed Tip messages growing in size after resolution change
- Slowmo is now disabled when Player dies
- Fixed rare "walking into a corner" bug

### New FGD

The FGD included with this mod contains 2 AngelScript entities, as well as other entities which were found to be in Postal III but they aren't in the original FGD.  
Place `Postal3Angel.fgd` next to `Postal3.fgd` and do the following:  
Add this: `@include "Postal3Angel.fgd"`  

at the top of `Postal3.fgd`, and you should be able to see these new entities in either Hammer or Hammer++.

### New Console Commands
Note: You can find more AngelScript-related console commands on the AngelScript Docs

- `wj_cam_anims` -- Disables shaky camera animations, by default it is enabled. Does not require cheats to disable. Does not disable HL2 shake events. (like grenade explosions)
- `wj_angelscript_recompile` -- Recompiles AngelScript code on the fly
- `wj_angelscript_recompile_alt` -- Instantly recompiles AngelScript code on the fly without clearing the console
- `wj_debug_print_p3s` -- Prints P3S data of an entity to the console you are currently looking at. Overlay can be toggled on or off.
- `wj_debug_print_p3s_held` -- Prints P3S data of an entity's held item to the console you are currently looking at. Overlay can be toggled on or off.
- `wj_debug_print_p3s_player` -- Prints P3S data of the Player to the console. Overlay can be toggled on or off.
- `wj_debug_print_p3s_weapon` -- Prints P3S data of the Player's held weapon to the console. Overlay can be toggled on or off.
- `wj_debug_player_takeitem` -- Takes an item and places it into the Player's hand.
- `wj_debug_force_hate` -- Forces an NPC to hate the Player which is currently under the crosshair
- `wj_debug_remove` -- Removes an entity under the crosshair
- `wj_debug_force_hate_target1` -- Saves target 1
- `wj_debug_force_hate_target2` -- Saves target 2
- `wj_debug_force_hate_infight` -- Starts infight between Target 1 and Target 2
- `wj_player_use_crosshair_distance` -- The distance the Player can use any entity (cheat)
- Cat, Beehive, Catnip Can/Spray, Seed (unused), Pepper Can/Spray, and Gasoline's max ammo are no longer hardcoded, these start with `sk_max_p3_`

### Extended Postal3Script capability

- Added `AngelScript` P3S function (Please visit the AngelScript Docs to better understand what this function does!)
- Animals now have `ImAnAnimal` hardcoded P3S attribute on spawn
- Human NPCs now have `ImAHuman` hardcoded P3S attribute on spawn
- Cats now have `ImACat` hardcoded P3S attribute on spawn
- Dogs now have `ImADog` hardcoded P3S attribute on spawn
- Monkeys (including Motorhead) now have hardcoded `ImAMonkey` P3S attribute on spawn
- Motorhead now has `ImMotorhead` hardcoded P3S attribute on spawn
- Helicopters now have `ImAHelicopter` hardcoded P3S attribute on spawn
- Pigeons now have `ImAPigeon` hardcoded P3S attribute on spawn (pigeons are still not recommended to use in maps, hardcoded AS calls not supported)
- Policemen now have `ImAPoliceman` hardcoded P3S attribute on spawn (Not really recommended to use p3_npc_cop, hardcoded AS calls not supported)
- Military now have `ImAMilitary` hardcoded P3S attribute on spawn (tactical NPCs, can use cover ability, etc..)
- Citizens now have `ImACitizen` hardcoded P3S attribute on spawn
- Rhinos now have `ImARhino` hardcoded P3S attribute on spawn
- Sim Drivers now have `ImASimDriver` hardcoded P3S attribute on spawn
- Hugo Chavez now has `ImHugoChavez` hardcoded P3S attribute on spawn (or also known as the Tank driver)
- Fixed P3S weapon scripting, all weapons now have a proper Postal3Script pointer which can be scripted (B:itmWeapon, M:itmWeapon, F:Items, I:itm_weapon, S:st_default)
- Added hardcoded P3S attribute `active` for weapons, if it's 1 they can be seen (not holstered), otherwise they are in someone's pocket
- Added hardcoded P3S attribute `dropped` for weapons, by default this is 0 on spawn so NPCs cannot target weapons
- Finished `pickup` param for `Weapon` Postal3Script function, NPCs can pickup weapons via scripting
- `Object:item` can now be used for getting the active weapon pointer in P3S (The check for a valid item goes like this: (Meta weapon -> Corpse weapon -> Weapon))
- `Object:item` now works on Players the same way it does for NPCs
- Fixed `Ignore` not working with corpses
- `EmitSound` now works with any P3 entity
- `Timer` can now have longer declarations
- `TargetItem` now works with Players too, and can now be used to target active weapon
- `TakeItem` now works with weapons for Human NPCs
- Added `OnPissed` P3S Event for FSM item entities
- Added timer `OnTimer_tNodeUsage` which is randomized between 10-22 seconds whenever a node was used, in CR this timer is used to prevent NPCs using nodes all the time
- Added `UnlockHintNode` P3S function (This should be called when NPCs exited out from the node's state, typically inside something like `pt_end`)
- Added `ea_glow` P3S attribute, if this attribute exists on entities, when the Player looks at them they'll glow as if they were an item
- Added `OnPlayerCrosshairFocus` and `OnPlayerCrosshairLeft` P3S events, they will execute on target entity the Player is looking at
- Added `OnApplyCatnipHead` P3S event for catnip weapon

### Hardcoded AngelScript Calls
Several hardcoded AngelScript calls have been added so modders can extend or modify behavior.  
For more information visit the AngelScript Docs

!!! note Note
	`CTakeDamageInfo@` functions are not hooks, the `info` pointer should only be read, setting damage will have no effect!

### Player only
+ `void Player::Spawn()`
+ `void Player::OnRestore()`
+ `void Player::OnHostageTaken()`
+ `void Player::OnHostageReleased_Killed()`
+ `void Player::OnNPCArrested()`
+ `void Player::OnTakeDamage(CTakeDamageInfo@ info)`
+ `void Player::Event_Killed(CTakeDamageInfo@ info)`

### NPC only
+ `void NPC::OnTakeDamage_Alive(CTakeDamageInfo@ info)`
+ `void NPC::OnTakeDamage_Dying(CTakeDamageInfo@ info)`
+ `void NPC::Event_Unconscious(CTakeDamageInfo@ info) (Animal/Human NPCs only)`
+ `void NPC::OnTakeDamage(CTakeDamageInfo@ info)`
+ `void NPC::Event_Killed(CTakeDamageInfo@ info)`

### SEngine only
+ `void SEngine::LevelInitPostEntity()`
+ `void SEngine::LevelInitPreEntity()`
+ `void SEngine::LevelShutdownPostEntity()`
+ `void SEngine::LevelShutdownPreEntity()`
+ `void SEngine::OnRestore()`
+ `void SEngine::OnSave()`
+ `void SEngine::Recompile()`
+ `void SEngine::PostInit()`
+ `void SEngine::FireGameEvent(IGameEvent@ evt)`
+ `void SEngine::OnCVarChanged(string name, string OldString, float OldValue)`