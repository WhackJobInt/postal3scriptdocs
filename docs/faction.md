# Faction
<p>Factions/Squads in Postal III are Half-Life 2 squads
<p>One Squad can hold 32 NPCs in one map, if it's higher than 32, problems might occur.
<pre><code class="language-js">
st_FactionTutorial
{
	Group Neutral
	Patterns
	{
		pt_default
		{
			actions
			{
				// Here you can find all the Factions defined in Vanilla Postal III
				IfAttr "ea_faction == Faction:Police Return 1"
				IfAttr "ea_faction == Faction:Zealots Return 1"
				IfAttr "ea_faction == Faction:Citizens Return 1"
				IfAttr "ea_faction == Faction:Hobos Return 1"
				IfAttr "ea_faction == Faction:Animals Return 1"
				IfAttr "ea_faction == Faction:Player Return 1"
				IfAttr "ea_faction == Faction:LaserDot Return 1"
				IfAttr "ea_faction == Faction:Effects Return 1"
				IfAttr "ea_faction == Faction:Items Return 1"
				IfAttr "ea_faction == Faction:Taliban Return 1"
				IfAttr "ea_faction == Faction:Venezuela Return 1"
				IfAttr "ea_faction == Faction:ZombieBoss Return 1" // used by flag_zombie (Boss NPCs)
				
				// Factions are independent from Squads
				
				// Setting a Squad in an NPC
				SetSquad tutorial_squad
				// Making another Squad an enemy
				SetSquadRelation player_squad:enemy
				
				// You can also do value after declaring enemy (todo: what does it do?)
				SetSquadRelation player_squad:enemy:4
			}
		}
	}
}
</code></pre>