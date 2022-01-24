# Engine Attributes
<p>Some of the engine's internal variables are exposed to Postal3Script, e.g. Health.
<p>These special Attributes are named as ea_*
<p>These attributes are heavily tied to the engine, breaking or changing them in an unnatural way is not advised.
<pre><code class="language-js">
st_SpecialAttrTutorial
{
	Group Neutral
	Patterns
	{
		pt_default
		{
			actions
			{
				// Special damage absorptions
				SetAttr "ea_dmg_absorb 70"
				SetAttr "ea_bulletdmg_absorb 90"
				SetAttr "ea_clubdmg_absorb 70"
				SetAttr "ea_flamedmg_absorb 20"
				SetAttr "ea_blastdmg_absorb 30"
				SetAttr "ea_krotchydmg_absorb 100"
				SetAttr "ea_flamedmg_absorb 100"
				SetAttr "ea_physdmg_absorb 90"
				SetAttr "ea_blast_immune 1"
				
				// NPC cannot do crit damage (kinda like in TF2)
				SetAttr "ea_crit_disabled 1"
				
				// NPC Faction check, please look at Factions
				IfAttr "ea_faction == Faction:Police SetAttr tutorial_imacop 1"
				
				// Health, if set to 0 NPC or Player will die
				IfAttr "ea_health < 55 SetAttr tutorial_imwounded 1"
				
				// NPC cannot be picked up (mainly used by Cats)
				SetAttr "ea_takeable 0"
				
				// NPC is no longer tased
				SetAttr "ea_tased 0"
				
				// NPC Manner, please look at Manners
				IfAttr "ea_Manner == Manner:JusticeMan State bh_human:st_attack_melee"
				
				// NPC Status, mainly used to determine if they are holding dangerous weapons
				SetAttr "ea_status sNEUTRAL"
				IfAttr "ea_armed == WPN_M16 SetAttr NumAmmo AMMO_M16_MAX"
				IfAttr "ea_ActiveWeapon == Weapon:Ranged Aim true,false"
				IfAttr "ea_NumEnemies == 0 and ea_NumFear == 0 SetAttr tutorial_calm 1"
				IfAttr "ea_NumVisibleEnemy == 0 SetAttr TaskCombat TC_SEARCH"
				
				// NPC will disappear if Player is too far away
				SetAttr "ea_autokill 0"
				
				// No gibbing
				SetAttr "ea_no_gibs 1"
				
				// Used for Segways
				IfAttr "ea_lean != 1 Pattern pt_lean_in"
				
				// NPC's Hammer name
				IfAttr "ea_name == String:npc_pizza_vendor SetAttr cr_vendor 1"
				
				// Ammo
				IfAttr "ea_HaveAmmo == 0 Pattern pt_reload"
				
				// Gibs
				CheckAttr "ea_gibs"
			}
		}
	}
}
</code></pre>