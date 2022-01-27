# Manner
<p>Each NPC and even some generic entities, have a specific Manner assigned to them. This is essentially the same thing as Faction but on a more individual level. 
This is used for various things, such as setting and checking how a specific NPC belonging to a faction actually BEHAVES to then make another NPC act accordingly towards them. For example, preventing us from punching someone we dislike, and instead just shoving them because our manner is set as "GayGuy".
<p>(TODO: Manner bias towards other NPC must be researched to fully understand it)
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
				// Here's a list of all Manners...
				IfAttr "ea_Manner == Manner:Player Return 1"
				IfAttr "ea_Manner == Manner:StreetBro Return 1"
				IfAttr "ea_Manner == Manner:JusticeMan Return 1"
				IfAttr "ea_Manner == Manner:StGranny Return 1"
				IfAttr "ea_Manner == Manner:LameWanker Return 1"
				IfAttr "ea_Manner == Manner:SoccerMom Return 1"
				IfAttr "ea_Manner == Manner:CuteGirl Return 1"
				IfAttr "ea_Manner == Manner:Vendor Return 1"
				IfAttr "ea_Manner == Manner:RedNeck Return 1"
				IfAttr "ea_Manner == Manner:SushiNinja Return 1"
				IfAttr "ea_Manner == Manner:Girl Return 1"
				IfAttr "ea_Manner == Manner:MedicDoc Return 1"
				IfAttr "ea_Manner == Manner:StrayDog Return 1"
				IfAttr "ea_Manner == Manner:MonkeyApe Return 1"
				IfAttr "ea_Manner == Manner:PussyCat Return 1"
				IfAttr "ea_Manner == Manner:JihadBeard Return 1"
				IfAttr "ea_Manner == Manner:RhinoCow Return 1"
				IfAttr "ea_Manner == Manner:LaserDot Return 1"
				IfAttr "ea_Manner == Manner:Mission Return 1"
				IfAttr "ea_Manner == Manner:Pigeon Return 1"
				IfAttr "ea_Manner == Manner:GayGuy Return 1"
				IfAttr "ea_Manner == Manner:NerdyNerd Return 1"
				IfAttr "ea_Manner == Manner:Bystander Return 1"

				// Don't continue if we're not a StreetBro...
				IfAttr "ea_manner != Manner:StreetBro Return 1"

				// If the target's manner is lame wanker, bully the poor guy!
				IfAttr "target.ea_manner == Manner:LameWanker Pattern pt_Bully"
			}
		}
	}
}
</code></pre>