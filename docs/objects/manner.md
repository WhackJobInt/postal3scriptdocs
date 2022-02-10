# Manner
<p>Each NPC and even some generic entities, have a specific Manner assigned to them. This is essentially the same thing as Faction but on a more individual level. 
This is used for various things, such as setting and checking how a specific NPC belonging to a faction actually BEHAVES to then make another NPC act accordingly towards them. For example, preventing us from punching someone we dislike, and instead just shoving them because our manner is set as "GayGuy".

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Here's a list of all the manner types:
<code>Player, StreetBro, JusticeMan, StGranny, LameWanker, SoccerMom, CuteGirl, Vendor, RedNeck, SushiNinja, Girl, MedicDoc, StrayDog, MonkeyApe, PussyCat, JihadBeard, RhinoCow, LaserDot, Mission, Pigeon, GayGuy, NerdyNerd, Bystander</code></p>
</div>

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