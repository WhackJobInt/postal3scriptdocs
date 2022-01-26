#- Weapon
<p>Sets NPC's current weapon state
<h1>Syntax</h1>
<p><code class="language-js">Weapon select, melee</code> -- Selects melee weapon, if available
<p><code class="language-js">Weapon select, ranged</code> -- Selects ranged weapon, if available
<p><code class="language-js">Weapon arm</code> -- Automatically selects weapon
<p><code class="language-js">Weapon disarm</code> -- Holsters active weapon
<p><code class="language-js">Weapon drop</code> -- Drops active weapon (won't drop if it's not out)
<h1>Example</h1>
<pre><code class="language-js">
// from ai_mission_pdb.p3s
st_OnSprayStunned
{	
	Group Alert
	Patterns
	{
		pt_default
		{
			actions
			{
				AreaEvent ENEMY,16
				// Drops weapon
				Weapon drop
				ExecutePattern bh_base:st_OnSprayStunned.pt_default
			}
		}
		
	}
}

// from ai_mission_srm.p3s
// This will unholster it's weapon and aim at the Player
pt_attack
{
	actions
	{
		Timer attacktimer,2:3,repeated
		TargetPlayer 1
		MoveToTarget false
		FreeMovement false
		Weapon Arm
		Aim true
		State st_hitit
	}

}
</code></pre>

<br><br><h1>- Reload</h1>
<p>Forces NPC to reload it's weapon
<h1>Syntax</h1>
<p><code class="language-js">Reload 1</code> -- Reloads
<h1>Example</h1>
<pre><code class="language-js">
// from ai_npc_military.p3s (stripped out)
pt_default
{
	actions 
	{
		IfAttr "ea_HaveAmmo == 0 Block begin"
			ExecutePattern st_reload.xpt_prereload
			Reload 1
			WaitForEnd 1
		Block end
		State st_start
	}
}
</code></pre>

<br><br><h1>- ThrowGrenade</h1>
<p>Forces NPC to throw a grenade
<h1>Syntax</h1>
<pre><code class="language-js">
// Grenade types
frag
smoke
flash
beenest
molotov
krotchy_toy
</code></pre>
<p><code class="language-js">ThrowGrenade 1, [grenade type], no_ally</code> -- Throws grenade, optional flag
<h1>Example</h1>
<pre><code class="language-js">
// This AI will do nothing but throw grenades at the Player every 5 seconds
behavior
{
	name bh_molotovthrower
	inherited bh_human
	States
	{
		st_start
		{
			Group Neutral
			Patterns
			{
				pt_default
				{
					actions
					{
						SetSquadRelation player_squad:enemy:10
						TargetPlayer 1
						Wait 1
						ThrowGrenade 1, molotov
						Repeat 5
					}
				}
			}
		}
	}
}
</code></pre>