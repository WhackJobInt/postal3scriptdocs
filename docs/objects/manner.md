# Manner
Each NPC and even some generic entities, have a specific Manner assigned to them.  
This is essentially the same thing as `Faction` but on a more individual level. 

This is used for various things, such as setting and checking how a specific NPC belonging to a `Faction` actually BEHAVES to then make another NPC act accordingly towards them.  
For example, preventing us from punching someone we dislike, and instead just shoving them because our `Manner` is set as `GayGuy`.

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Here's a list of all the manner types:
<code>Player</code>, <code>StreetBro</code>, <code>JusticeMan</code>, <code>StGranny</code>, <code>LameWanker</code>, <code>SoccerMom</code>, <code>CuteGirl</code>, <code>Vendor</code>, <code>RedNeck</code>, <code>SushiNinja</code>, <code>Girl</code>, <code>MedicDoc</code>, <code>StrayDog</code>, <code>MonkeyApe</code>, <code>PussyCat</code>, <code>JihadBeard</code>, <code>RhinoCow</code>, <code>LaserDot</code>, <code>Mission</code>, <code>Pigeon</code>, <code>GayGuy</code>, <code>NerdyNerd</code>, <code>Bystander</code></p>
</div>

!!! error "Bug"
	- There is an identification mismatch between source code and the Manner list, a dummy Manner should be added at the very top (first on the list) to avoid issues.  
	- When checking for Manner, the Manner **MUST** exist in the list of Manners, otherwise Postal3Script will pass checks for that entity unknowingly.

<pre><code class="language-js">
st_MannerTutorial
{
	Group Neutral
	Patterns
	{
		pt_default
		{
			actions
			{
				// Don't continue if we're not a StreetBro...
				IfAttr "ea_manner != Manner:StreetBro Return 1"

				// If the target's manner is lame wanker, bully the poor guy!
				IfAttr "target.ea_manner == Manner:LameWanker Pattern pt_Bully"
			}
		}
	}
}
</code></pre>