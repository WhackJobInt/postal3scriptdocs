# Embedded Attributes
Instead of unexposed C++ variables in the source code, there are attributes that are already "embedded" and read from a related Postal3Script for given entities.

For example, "ea_health" is the health of the entity that uses the assigned p3s behaviour, or the health of a set target, and can be read, changed, and set using the various "Attr" statements.

There are a variety of attributes and they each serve their own purposes.

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Embedded Attributes have the <code>ea_</code> prefix.</p>
</ul>
</div>

## 🆙🪽 Ultrapatch Embedded Attributes
!!! warning "🆙🪽 Postal III Ultrapatch-only feature"
	These embedded attributes below will only work with Postal III Ultrapatch.
```
ImAnAnimal				-- Entity is an animal NPC, if it exist
ImAHuman				-- Entity is a Human NPC, if it exist
ImACat					-- Entity is a Cat NPC, if it exist
ImADog					-- Entity is a Dog NPC, if it exist
ImAMonkey				-- Entity is a Monkey NPC, if it exist
ImMotorhead				-- Entity is Motorhead, if it exist
ImAHelicopter			-- Entity is a Helicopter, if it exist
ImAPigeon				-- Entity is a Pigeon NPC, if it exist
ImAPoliceman			-- Entity is an unused Policeman-type Human NPC, if it exist
ImAMilitary				-- Entity is a Military-type Human NPC, if it exist
ImACitizen				-- Entity is a Citizen-type Human NPC, if it exist
ImARhino				-- Entity is a Rhino-type Animal NPC, if it exist
ImASimDriver			-- Entity is a Sim Driver-type Citizen NPC, if it exist
ImHugoChavez			-- Entity is Hugo Chavez Sim Driver NPC, if it exist

ea_glow					-- Entity will glow if Player looks at it, if it exist
active					-- (Weapon) If it's 1 they can be seen, not holstered
dropped					-- (Weapon) By default (on spawn) is 0

flag_boss				-- NPC is a boss, used for missions and achievements, if it exist
```

## 🪽 Angel Embedded Attributes
!!! warning "🪽 Postal III Ultrapatch Angel-only feature"
	These embedded attributes below will only work with Postal III Ultrapatch Angel.
```
ea_allowpickup			-- (Interactable prop) Pick up is allowed, if it exist
ea_propMotion			-- (Interactable prop) Motion is enabled on hurt, if it exist
ea_touch				-- (Interactable prop) Entity is able to feel, if it exist

as_restore				-- Fires OnASRestore on save game load on the entity, if it exist
as_transition			-- Fires OnASTransition on transition load on the entity, if it exist
```

## All Embedded Attributes
<pre><code>
flag_zombie				-- NPC is a boss, used for missions and achievements, if it exist
flag_bystander			-- NPC is a bystander, used for missions and achievements, if it exist
SnatchBiteDamage		-- Used for overriding snatch bite damage for animals

ea_lean					-- Whether NPC or Player is currently covering
ea_consciousness		-- Gets or sets the consciousness of an NPC, setting it to zero does nothing
ea_health				-- Health
ea_status				-- Status (Killer, Victim, Corpse, etc..)
ea_armed				-- Stored/Active Weapon ID
ea_hostage				-- Whether the Player currently has a hostage
ea_NumEnemy				-- Number of enemies
ea_NumFear				-- Number of fear enemies
ea_NumVisibleEnemy		-- Number of visible enemies
ea_NumVisibleFear		-- Number of visible fear enemies
ea_ammo					-- Gets the Ammo of NPC's weapon (broken)
ea_Faction				-- Faction
ea_Manner				-- Manner
ea_ActiveWeapon			-- Gets the weapon type
-1 	= FLESH
 0 	= NONE
 1 	= ANIMAL
 2 	= GADGET
 3 	= NONLETHAL_MELEE
 4 	= NONLETHAL_RANGED
 5 	= MELEE
 6 	= RANGED
 7 	= BIGGUN
 
ea_games				-- Whether the Player is currently peeing (0 if they aren't)
ea_takeable				-- Player can interact with Cat/Human by pressing USE on them
ea_distance				-- UNUSED, won't do anything
ea_name					-- Given name by the mapper to the entity
ea_crit_disabled		-- Taken crit damage (is this a leftover from TF2?)
ea_no_gibs				-- NPC's limbs can no longer be deattached if died
ea_dmg_absorb			-- ALL Damage type absorption
ea_flamedmg_absorb 		-- Flame DMG absorption (DMG_BURN)
ea_bulletdmg_absorb 	-- Bullet DMG absorption (DMG_BULLET)
ea_clubdmg_absorb		-- Club DMG absorption (DMG_CLUB)
ea_physdmg_absorb		-- Physics DMG absorption (DMG_CRUSH)
ea_fakedmg_absorb		-- UNUSED (DMG_PHYSGUN), this attribute still works and functions
ea_blastdmg_absorb		-- Blast Explosion DMG absorption (DMG_BLAST)
ea_krotchydmg_absorb 	-- Krotchy DMG absorption (DMG_BUCKSHOT), parallel to Blast DMG
ea_blast_immune			-- Blast from Explosion immunity, boltons won't fall off from the NPC
ea_tased				-- Whether the NPC is currently tased
ea_autokill				-- NPC will disappear if it's too far from the Player (1920 Hammer units)
ea_gibs					-- Only exists on ragdolls
 1 	= Full body/Lower body/Lower body with legs
 3 	= Single Head/Upper body with head (and arms)
 4 	= Single Arm/Single Leg/Upper body (with arms)
</code></pre>
<br>

## Embedded Attribute Example
<pre><code class="language-js">
st_EmbeddedAttrTutorial
{
	Group Neutral
	Patterns
	{
		pt_default
		{
			actions
			{
				SetAttr "covering 0"
				IfAttr "ea_lean == 1 SetAttr covering 1"
				
				SetAttr "ea_consciousness 120"
				SetAttr "ea_health 100"
				
				IfAttr "target.ea_status == sCORPSE Pattern pt_eeek"
				
				IfAttr "ea_armed != WPN_NONE Pattern pt_gungun"
				IfAttr "ea_hostage == 1 Pattern pt_victim"
				
				IfAttr "ea_NumEnemy > 0 Pattern pt_seek"
				IfAttr "ea_NumFear > 0 Pattern pt_fear"
				IfAttr "ea_NumVisibleEnemy > 0 Pattern pt_destroy"
				IfAttr "ea_NumVisibleFear > 0 Pattern pt_hide"
				
				// Note: ea_ammo is broken
				IfAttr "ea_ammo == 0 Pattern pt_reload"
				
				IfAttr "ea_Faction == Faction:Player Pattern pt_player"
				IfAttr "ea_Manner == Manner:Police Pattern pt_police"
				
				IfAttr "Object:target == Object:Player AND ea_ActiveWeapon < 6 Pattern pt_meleeOnly"
				
				IfAttr "Object:target == Object:Player AND target.ea_games == 1 Pattern pt_yuck"
				
				SetAttr "ea_takeable 0"
				
				IfAttr "ea_name == String:pizza_vendor State st_vendor"
				
				SetAttr "ea_crit_disabled 1"
				SetAttr "ea_no_gibs 1"
				
				SetAttr "ea_dmg_absorb 50"
				SetAttr "ea_flamedmg_absorb 50"
				SetAttr "ea_clubdmg_absorb 50"
				SetAttr "ea_physdmg_absorb 50"
				SetAttr "ea_fakedmg_absorb 50"
				SetAttr "ea_blastdmg_absorb 50"
				SetAttr "ea_krotchydmg_absorb 50"
				
				SetAttr "ea_blast_immune 1"
				
				CheckAttr "ea_tased RemoveAttr ea_tased"
				
				SetAttr "ea_autokill 1"
			}
		}
	}
}
</code></pre>