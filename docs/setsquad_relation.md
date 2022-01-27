<h1>Note: One squad can only hold 32 NPCs in one map
<br><h1>- SetSquad</h1>
<p>Sets an NPC's squad
<h2>Syntax</h2>
<p><code class="language-js">SetSquad [string]</code> - Sets squad
<p><code class="language-js">SetSquad null</code> - Clears out squad
<h1>Example</h1>
<pre><code class="language-js">
// (from ai_mission_pwac)
st_init
{
	Group Neutral
	
	Patterns
	{
		pt_default
		{
			actions
			{
				ExecutePattern bh_base:st_init.pt_default
				
				SetAttr "GrenadeType GRND_TYPE_FRAG"
				SetAttr "flag_ThrowSafe 1"
				
				// Set our squad as Cops_squad
				SetSquad Cops_squad
				SetSquadRelation Prison_squad:enemy:2,Player_squad:enemy:4
			}
		}
	}
}
</code></pre>

<br><br><h1>- SetSquadRelation</h1>
<p>Sets an NPC's squad's relation towards another squad
<h2>Syntax</h2>
<p><code class="language-js">SetSquadRelation [squad name]:[neutral/enemy/fear]:[priority]</code> -- use commas (,) to set more relations
<h1>Example</h1>
<pre><code class="language-js">
// (from ai_mission_jwb)
pt_default
{
	actions
	{
		ExecutePattern bh_base:st_init.pt_default
		
		TargetEntByName "mission_logic"
		TargetToMem msGP
		FireEvent CopSpawned
		
		SetSquad cop_squad
		// Hates Player, and Soccer Moms, but hates the latter more
		SetSquadRelation Player_squad:enemy:3,SoccerMom:enemy:1
		
		SetAttr "IdleTask 0"
		SetAreaGroup AG_DEFAULT,AG_BATTLE,AG_SHOP
	}
}
</code></pre>

<br><br><h1>- RemoveSquadRelation</h1>
<p>Unused Postal3Script function
<p>Removes an NPC's squad's relation towards another squad
<h2>Syntax</h2>
<p><code class="language-js">RemoveSquadRelation [squad name],[squad name]</code>
<p><code class="language-js">RemoveSquadRelation clear_all</code> -- Clears every squad relation from current squad