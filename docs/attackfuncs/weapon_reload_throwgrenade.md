# Weapon-related Functions

## Weapon

Sets NPC's current weapon state.

<h1>Syntax</h1>
<p><code class="language-js">Weapon select,melee</code> -- Selects melee weapon, if available</p>
<p><code class="language-js">Weapon select,ranged</code> -- Selects ranged weapon, if available</p>
<p><code class="language-js">Weapon arm</code> -- Automatically selects weapon</p>
<p><code class="language-js">Weapon disarm</code> -- Holsters active weapon</p>
<p><code class="language-js">Weapon drop</code> -- Drops active weapon (won't drop if it's not out)</p>
<h1>Example</h1>
<pre><code class="language-js">
// From ai_mission_pdb.p3s
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

// From ai_mission_srm.p3s
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

<br>
## Reload

Forces NPC to play reloading animation.

<h1>Syntax</h1>
<p><code class="language-js">Reload 1</code> -- Reloads</p>
<h1>Example</h1>
<pre><code class="language-js">
// From ai_npc_military.p3s (stripped out)
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

<br>
## ThrowGrenade

Forces NPC to throw a grenade

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Smoke and Flash grenade are never used anywhere else in the game.</p>
<p>Flash isn't recommended to use as it'll apply a permanent sound altering effect.</p>
</div>

<h1>Syntax</h1>
<pre><code class="language-js">
// Grenade types
frag
smoke -- Unused
flash -- Unused (not recommended to use this)
beenest
molotov
krotchy_toy
</code></pre>
<p><code class="language-js">ThrowGrenade 1,[grenade type],[no_ally]</code> -- Throws grenade, optional flag
<h1>Example</h1>
<pre><code class="language-js">
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
						// Do nothing but throw molotovs at the Player every 5 seconds
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