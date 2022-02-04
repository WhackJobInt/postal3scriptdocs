# Faction
<p>Each NPC, and even some generic entities, are set to belong to a specific faction. This is used for various things, such as checking for how we should act 
towards whole groups of specific NPC's, and what dispositions we should have against them.
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
				// Here's a list of all Factions...
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
				IfAttr "ea_faction == Faction:ZombieBoss Return 1" // Used by flag_zombie (Boss NPCs)

				// If our target is an animal, say we hate all animals!
				IfAttr "target.ea_faction == Faction:Animals pt_SayHateAllAnimals"
			}
		}
	}
}
</code></pre>