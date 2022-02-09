# Faction
<p>Each NPC, and even some generic entities, are set to belong to a specific faction. This is used for various things, such as checking for how NPC's should act 
towards whole groups of specific NPC's, and what dispositions they should have against them.

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Here's a list of all the faction types:
<code>Police, Zealots, Citizens, Hobos, Animals, Player, LaserDot, Effects, Items, Venezuela, ZombieBoss</code></p>
<p>The <code>ZombieBoss</code> faction is used for all boss NPC's, this is a quick hack so they won't invalidate the PERSONAL JESUS achievement
since zombies don't invalidate it</p>
</div>

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