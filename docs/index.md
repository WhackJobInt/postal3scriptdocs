# Home

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>This site is a Work in Progress! Many functions are still not covered yet, or those that are already covered, their documentation are subject to change!</p>
<p><b>Last Update: <i>01.11.2024</i></b> (<a href="changelog.md">Changelog</a>)</p>
</div>

!!! tip "Did You Know?"
    - There are a total of 125 Postal3Script functions.
	- NPCs/Entities with no P3S behavior defined will fallback to the `default_behavior` behavior

## Postal3Script
<ul>
<li><a href="whatispostal3script.md">What is Postal3Script?</a></li>
<li><a href="debugging.md">Debugging Postal3Script</a></li>
<li><a href="wipp3sfiles.md">Development/WIP Files</a></li>
<li><a href="syntaxhighlighter.md">Syntax Highlighter</a></li>
</ul>

## Embedded (Hardcoded)/Engine
<ul>
<li><a href="attribchecking/embedattributes.md">Embedded Attributes</a></li>
<li><a href="embeddedevents.md">Embedded Events</a></li>
<li><a href="embeddedbehaviors.md">Embedded Behaviors</a></li>
<li><a href="animationsevents.md">Animation Events</a></li>
<li><a href="inputfunctions.md">Input Functions</a></li>
</ul>

## Tutorials
- [Events](events.md)
- [Blocks, Conditional](blocksconditional.md)
- [States, Patterns, Execution Patterns](statespatterns.md)
- [Randomization](randomization.md)

## Attribute Checking
<ul>
<li><a href="attribchecking/attributes.md">IfAttr, SetAttr, CheckAttr, ChangeAttr, RemoveAttr</a></li>
</ul>

## Object Categories
<ul>
<li><a href="objects/manner.md">Manner</a></li>
<li><a href="objects/faction.md">Faction</a></li>
<li><a href="objects/itemtype.md">ItemType</a></li>
<li><a href="objects/string.md">String</a></li>
<li><a href="objects/timer.md">Timer</a></li>
<li><a href="objects/object.md">Object</a></li>
<li><a href="objects/distto.md">DistTo</a></li>
<li><a href="objects/angleto.md">AngleTo</a></li>
<li><a href="objects/visible.md">Visible</a></li>
<li><a href="objects/hasweapon.md">HasWeapon</a></li>
<li><a href="objects/relationto.md">RelationTo</a></li>
<li><a href="objects/relation.md">Relation</a></li>
<li><a href="objects/name.md">Name</a></li>
<li><a href="objects/ammo.md">Ammo</a></li>
<li><a href="objects/ignore.md">Ignore</a></li>
<li><a href="objects/karma.md">Karma</a></li>
<li><a href="objects/voiceprefix.md">VoicePrefix</a></li>
</ul>

## State Functions
- [State, Pattern, ExecutePattern](statefuncs/func_state_pattern_executepattern.md)
- [Wait, WaitForEnd, Repeat, Return](statefuncs/wait_waitforend_repeat.md)
- [StateMatrix](statefuncs/statematrix.md)
- [CallState, CallPattern](statefuncs/callstate_callpattern.md)
- [StoreActivityPattern, ExecuteActivityPattern, ClearActivityPattern](statefuncs/activitypattern_funcs.md)
- [SendState, SendPattern](statefuncs/sendstate_sendpattern.md)

## Misc Functions
<ul>
<li><a href="miscfuncs/areaevent.md">AreaEvent</li></li>
<li><a href="miscfuncs/effect.md">Effect</li></li>
<li><a href="miscfuncs/fire_event_and_user_funcs.md">FireEvent, FireEventEx, FireUser, OnUser, FireInput, EntFireUser, EntFireInput</li></li>
<li><a href="miscfuncs/item_spawnitem.md">Item, SpawnItem</li></li>
<li><a href="miscfuncs/addfluid.md">AddFluid</li></a>
<li><a href="miscfuncs/anchor.md">Anchor, TargetAnchor</li></a>
</ul>

## NPC Functions
<ul>
<li><a href="npcfuncs/say.md">Say</li></a>
<li><a href="npcfuncs/emitsound.md">EmitSound</li></a>
<li><a href="npcfuncs/gesture_resetgesture_resetsequence.md">Gesture, ResetGesture, Sequence, ResetSequence</li></a>
<li><a href="npcfuncs/headblob.md">Headblob</li></a>
<li><a href="npcfuncs/NPC.md">NPC</li></a>
</ul>

## NPC Behavior Functions
<ul>
<li><a href="npcbehaviorfuncs/aim_face.md">Aim, Face</li></a>
<li><a href="npcbehaviorfuncs/snatch_unsnatch.md">Snatch, Unsnatch</li></a>
<li><a href="npcbehaviorfuncs/senses_lookat_lookout.md">Senses, LookAt, LookOut</li></a>
<li><a href="npcbehaviorfuncs/crouch_lean.md">Crouch, Lean</li></a>
<li><a href="npcbehaviorfuncs/busy_hate.md">Busy, Hate</li></a>
<li><a href="npcbehaviorfuncs/follow_playerfriendly.md">Follow, PlayerFriendly</li></a>
<li><a href="npcbehaviorfuncs/catdervish.md">CatDervish</li></a>
<li><a href="npcbehaviorfuncs/stunout.md">StunOut</li></a>
<li><a href="npcbehaviorfuncs/enablegibs.md">EnableGibs</li></a>
<li><a href="npcbehaviorfuncs/entervehicle.md">EnterVehicle</li></a>
</ul>

## Squad Functions
<ul>
<li><a href="squadfuncs/setsquad_relation.md">SetSquad, SetSquadRelation, RemoveSquadRelation</li></a>
<li><a href="squadfuncs/rallysquad.md">RallySquad</li></a>
</ul>

## Targeting Functions
<ul>
<li><a href="targetingfuncs/targetentbyname.md">TargetEntByName</li></a>
<li><a href="targetingfuncs/sendtarget2caller_sendcaller.md">SendTarget2Caller, SendCaller</li></a>
<li><a href="targetingfuncs/checktarget_checklos.md">CheckTarget, CheckLOS</li></a>
<li><a href="targetingfuncs/reset_ignore_settarget.md">ResetTarget, IgnoreTarget, SetTarget</li></a>
<li><a href="targetingfuncs/targetfunctions.md">TargetEnemy, TargetPlayer, TargetCaller, TargetItem, TargetVehicle, TargetHostage, TargetCrosshair</li></a>
<li><a href="targetingfuncs/targetmemory.md">TargetToMem, TargetFromMem, CallerToMem, ClearMem</li></a>
<li><a href="targetingfuncs/assisttarget_enemy.md">AssistTarget, AssistEnemy, ArrestTarget, BusyTarget</li></a>
<li><a href="targetingfuncs/relationship.md">Relationship</li></a>
</ul>

## Movement Functions
<ul>
<li><a href="movementfuncs/movement_funcs.md">Move, MoveToLean, MoveToTarget, MoveToTargetLKP</li></a>
<li><a href="movementfuncs/freemovement.md">FreeMovement, FreeMovementParams</li></a>
<li><a href="movementfuncs/travelbypathtrack.md">TravelByPathTrack</li></a>
<li><a href="movementfuncs/sethint_area_leangroup_avoidarea.md">SetHintGroup, SetAreaGroup, SetLeanGroup, AvoidProhibitedArea</li></a>
<li><a href="movementfuncs/turn_turnspeed.md">Turn, TurnSpeed</li></a>
<li><a href="movementfuncs/setactpack.md">SetActPack</li></a>
</ul>

## Attack Functions
<ul>
<li><a href="attackfuncs/hit.md">Hit</li></a>
<li><a href="attackfuncs/push.md">Push</li></a>
<li><a href="attackfuncs/weapon_reload_throwgrenade.md">Weapon, Reload, ThrowGrenade</li></a>
</ul>

## Mission Functions
<ul>
<li><a href="missionfuncs/attributeprogressbar.md">AttributeProgressBar</li></a>
<li><a href="missionfuncs/missionlog_save_briefing.md">MissionLog, MissionSave, MissionBriefing</li></a>
<li><a href="missionfuncs/showmessage_showhint.md">ShowMessage, ShowHint</li></a>
<li><a href="missionfuncs/endmission.md">EndMission</li></a>
<li><a href="missionfuncs/playerkarma.md">PlayerKarma</li></a>
<li><a href="missionfuncs/playvideo.md">PlayVideo</li></a>
<li><a href="missionfuncs/opendialog.md">OpenDialog</li></a>
</ul>

## Deleted Functions
<ul>
<li><a href="deletedfuncs/actbusy.md">ActBusy</li></a>
<li><a href="deletedfuncs/arm.md">Arm</li></a>
<li><a href="deletedfuncs/holsterweapon.md">HolsterWeapon</li></a>
<li><a href="deletedfuncs/desertsquad.md">DesertSquad</li></a>
<li><a href="deletedfuncs/fear.md">Fear</li></a>
</ul>

## Mission Script Files (Pre-Path)
1. [Paradise Bridge `PDB`](missions/pdb.md)
2. [Porn World `PW`](missions/pw.md)
3. [Diseased Cat Roundup `DCR`](missions/dcr.md)
4. [Jen Walcotts Bodyguard `JWB`](missions/jwb.md)
5. [Cash Mart Robbery `CM`](missions/cm.md)

## Mission Script Files (Good Path)

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Work in Progress</p>
</div>

## Mission Script Files (Evil Path)

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Work in Progress</p>
</div>