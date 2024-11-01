# Movement Functions

## Move

Sets the NPC's movement

<h1>Syntax</h1>
<p><code class="language-js">Move run</code> -- NPC will now run</p>
<p><code class="language-js">Move walk</code> -- NPC will now walk</p>
<p><code class="language-js">Move true</code> -- NPC is able to move</p>
<p><code class="language-js">Move false</code> -- NPC is no longer able to move</p>
<p><code class="language-js">Move [walk/run],[angle],[timing],[face_dir/update_dir]</code> -- todo</p>

<br>
## MoveToLean

Moves the NPC to a lean spot, used for combat

<h1>Syntax</h1>
<pre><code class="language-js">
// ENEMY DISTANCE (from ai_st_init.p3s)
Const ED_VERY_CLOSE,32
Const ED_CLOSE,160
Const ED_MIDDLE,320
Const ED_FAR,768
Const ED_FURTHER,1280
Const ED_VERY_FAR,2048

// Flags
nearest
nearest_to_target
in_viewcone
visible
notvisible_totarget
far
check_dotproduct
check_onmoving
not_behind_target
safe
area_group
</code></pre>
<p><code class="language-js">MoveToLean run,[distance_min],[distance_max],[flag1],[flag2],[flag3], ..</code></p>
<h1>Example</h1>
<pre><code class="language-js">
// from ai_cashmart.p3s
st_combat_hide
{
	Group Combat
	Patterns
	{
		pt_hide_param
		{
			actions 
			{
				ExecutePattern st_combat_logic.xpt_setAreaGroup
				MoveToLean run,ED_CLOSE,ED_FAR,notvisible_totarget
				Pattern pt_hide_loop
			}
		}
	}
}
</code></pre>

<br>
## MoveToTarget

Forces the NPC to move to it's target

<h1>Syntax</h1>
<pre><code class="language-js">
// Flags
none
to_target
from_target
target_dir
</code></pre>

<div class="admonition warning">
<p class="admonition-title">TODO</p>
<p>The syntax below is not really correct, It's not clear what each argument does just by looking at p3s scripts, it's a rough estimation</p>
</div>

<p><code class="language-js">MoveToTarget [run/walk/true],[distance_min],[distance_max],[flag]</code></p>
<p><code class="language-js">MoveToTarget [run/walk/true],[distance],[flag]</code></p>
<p><code class="language-js">MoveToTarget [false]</code></p>
<pre><code class="language-js">
// from ai_mission_sbe.p3s
pt_chase
{
	actions
	{
		TargetEntByName npc_slave
		MoveToTarget run,1
		CheckTarget 1
		Repeat 1
	}
	events
	{
		OnTimer_tChaseSlave "Pattern pt_stop_chase"
	}
}
</code></pre>

<br>
## MoveToTargetLKP

Forces the NPC to move to it's target's Last Known Position from the NPC's memory.

<h1>Syntax</h1>
<p><code class="language-js">MoveToTargetLKP [run/walk/true]</code>