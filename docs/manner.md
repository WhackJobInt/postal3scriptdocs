# Manner
<p>Manner alters the behavior of NPCs heavily, for e.g. they are less likely to attack a Cop than the Player.
<p>Manner bias towards other NPC must be researched to fully understand it
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
				// Here you can find all the Manners defined in Vanilla Postal III
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
			}
		}
	}
}
</code></pre>