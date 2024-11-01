# Faction
Each NPC, and even some generic entities, are set to belong to a specific `Faction`.  
This is used for various things, such as checking for how NPC's should act towards whole groups of specific NPC's, and what dispositions they should have against them.


!!! note "Note"
	Here's a list of all the faction types:  
	<code>Police</code>, <code>Zealots</code>, <code>Citizens</code>, <code>Hobos</code>, <code>Animals</code>, <code>Player</code>, <code>LaserDot</code>, <code>Effects</code>, <code>Items</code>, <code>Venezuela</code>, <code>ZombieBoss</code>  
	
	The <code>ZombieBoss</code> faction is used for all boss NPC's, this is a quick hack so they won't invalidate the <code>PERSONAL JESUS</code> achievement since zombies don't invalidate it

!!! error "Bug"
	- There is an identification mismatch between source code and the Faction list, a dummy Faction should be added at the very top (first on the list) to avoid issues.  
	- When checking for Faction, the Faction **MUST** exist in the list of Factions, otherwise Postal3Script will pass checks for that entity unknowingly.

!!! tip "🆙🪽 Postal III Ultrapatch-only feature"
	The '0 index' bug is fixed

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
				// If our target is an animal, say we hate all animals!
				IfAttr "target.ea_faction == Faction:Animals pt_SayHateAllAnimals"
			}
		}
	}
}
</code></pre>