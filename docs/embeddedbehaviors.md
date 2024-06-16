# Embedded Behaviors
Embedded Behaviors are the default hardcoded AIs which Postal 3 sets to certain entities on map load.

These behaviors can be given an AI (if they are unused) providing an actual script file with the behavior name.

!!! tip "Tip"
    The '**?**' symbol in the tables mean they can be overridden by the entity's existing key values.  
	If there are no hardcoded default values, it'll fallback to the **Default AI**'s values.

<br>

## Default AI (Error/Missing Behavior)

!!! note "Note"
    Postal 3 will fallback to this behavior if a behavior name couldn't be found, or it has too many errors in them.
	
!!! warning "Warning"
    - <code>default_behavior</code> won't override init and start states if they were pre-defined in some way.
	- <code>Manner</code> and <code>Faction</code> will re-use parameters from the entity.

| Behavior Name			| Init State 				| Start State 	 		| Manner 	| Faction 	|
|-----------------------|---------------------------|-----------------------|-----------|-----------|
| default_behavior		| st_def_init **(?)**       | st_default **(?)** 	| **?**		| **?**		|

<br>

## Anchor AI

!!! note "Note"
    <code>Anchor</code> function will spawn an entity with this AI. **Unused.**

| Behavior Name			| Init State 				| Start State 	 		| Manner 	| Faction 	|
|-----------------------|---------------------------|-----------------------|-----------|-----------|
| Anchor				| st_def_init       		| st_default 			| Anchor	| Anchor	|

<br>

## Weapon AI

!!! note "Note"
    All weapons in the game have this AI. **Unused.**

!!! warning "Broken Feature"
    Scriptable weapons are not possible, weapons will not have any working P3S scripting attached to them.
	
!!! tip "🪽 Postal 3 Angel-only feature"
	Postal 3 Angel has fixed this AI, and is working correctly.

| Behavior Name			| Init State 				| Start State 	 		| Manner 	| Faction 	|
|-----------------------|---------------------------|-----------------------|-----------|-----------|
| itmWeapon				| itm_weapon       			| st_default 			| itmWeapon	| Items		|

<br>

## Flame FX AI

!!! note "Note"
    Any entity on fire will have a second entity spawned on them with this AI.

| Behavior Name			| Init State 				| Start State 	 		| Manner 	| Faction 	|
|-----------------------|---------------------------|-----------------------|-----------|-----------|
| Flame					| fx_init_flame       		| fx_flame 				| Flame		| Effects	|

<br>

## Catnip Mark AI

!!! note "Note"
    Spraying catnip will spawn an entity with this AI.

| Behavior Name			| Init State 				| Start State 	 		| Manner 	| Faction 	|
|-----------------------|---------------------------|-----------------------|-----------|-----------|
| bh_catnip_dot			| catnip_init       		| catnip 				| Catnip	| Effects	|

<br>

## Catnip AI

!!! note "Note"
    Catnip on the ground. **Unused.**

| Behavior Name			| Init State 				| Start State 	 		| Manner 	| Faction 	|
|-----------------------|---------------------------|-----------------------|-----------|-----------|
| default_behavior		| st_def_init       		| itm_catnip 			| itmCatnip	| Items		|

<br>

## Laserdot AI

!!! note "Note"
    The Laser's AI that comes out from the Player's laserpen.

| Behavior Name			| Init State 				| Start State 	 		| Manner 	| Faction 	|
|-----------------------|---------------------------|-----------------------|-----------|-----------|
| bh_laserdot			| st_init_laserdot       	| st_laserdot 			| LaserDot	| LaserDot	|

<br>

## Player AI

!!! note "Note"
    The Player's AI.

| Behavior Name			| Init State 				| Start State 	 		| Manner 	| Faction 	|
|-----------------------|---------------------------|-----------------------|-----------|-----------|
| bh_player				| st_player_init       		| st_player 			| Player	| Player	|

<br>

## Corpse AI

!!! note "Note"
    The corpse's AI. Reuses the victim's behavior, manner, and faction.

| Behavior Name			| Init State 				| Start State 	 		| Manner 	| Faction 	|
|-----------------------|---------------------------|-----------------------|-----------|-----------|
| **?**					| st_init_corpse       		| st_corpse 			| **?**		| **?**		|

<br>

## Motorhead AI

!!! note "Note"
    Motorhead's AI.

| Behavior Name			| Init State 				| Start State 	 		| Manner 	| Faction 	|
|-----------------------|---------------------------|-----------------------|-----------|-----------|
| bh_motorhead			| st_init       			| st_start 				| MonkeyApe	| Animals	|

<br>

## Monkey AI

!!! note "Note"
    Monkey's AI (not Motorhead). Start and init states won't be overridden if they were already defined in the map.  
	If there's no pre-defined behavior name then it'll fallback to **default_behavior**.

| Behavior Name				| Init State 					| Start State 	 		| Manner 	| Faction 	|
|---------------------------|-------------------------------|-----------------------|-----------|-----------|
| **?**						| p3_wild_monkey_init **(?)** 	| p3_wild_monkey **(?)**| MonkeyApe	| Animals	|

<br>

## Krotchy Grenade AI

!!! note "Note"
    Krotchy Grenade's AI. **Unused.**

| Behavior Name			| Init State 				| Start State 	 		| Manner 		| Faction 	|
|-----------------------|---------------------------|-----------------------|---------------|-----------|
| default_behavior		| st_def_init       		| itm_toy 				| itmKrotchyToy	| Items		|

<br>

## Seed AI

!!! note "Note"
    Leftover from unfinished Seed weapon. The projectile's AI. **Unused.**

| Behavior Name			| Init State 				| Start State 	 		| Manner 		| Faction 	|
|-----------------------|---------------------------|-----------------------|---------------|-----------|
| default_behavior		| st_def_init       		| itm_seed 				| itmSeed		| Items		|

<br>

## Taser FX AI

!!! note "Note"
    Taser's beam AI. **Unused.**

| Behavior Name			| Init State 				| Start State 	 		| Manner 		| Faction 	|
|-----------------------|---------------------------|-----------------------|---------------|-----------|
| default_behavior		| st_def_init       		| fx_taserbeam 			| fxTaserBeam	| Effects	|

<br>