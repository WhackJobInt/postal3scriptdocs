#- FreeMovement
<p>Sets or resets NPC's freedom of movement.
<p>FreeMovementParams can be reset optionally.
<h1>Syntax</h1>
<p><code class="language-js">FreeMovement [walk/run],[reset]</code> -- NPC will walk or run, [reset] is optional
<p><code class="language-js">FreeMovement [true/false],[reset]</code> -- NPC can move or not, [reset] is optional
<p><code class="language-js">FreeMovement random,[reset]</code> -- Chooses between walk or run, [reset] is optional
<h1>Example</h1>
<pre><code class="language-js">
// (From ai_cashmart_npc.p3s)
// This will reset the NPC's movement to be able to move everywhere
xpt_invalidroute
{
	actions
	{
		Face false
		Crouch false
		Aim false
		FreeMovementParams area_all,-1,-1,area_group,once
		FreeMovement run,reset
	}
}
</code></pre>

<br><br><h1>- FreeMovementParams</h1>
<p>Restricts NPC's movement with parameters
<pre><code class="language-js">
// (From ai_st_init.p3s)
Const ED_VERY_CLOSE,32
Const ED_CLOSE,160
Const ED_MIDDLE,320
Const ED_FAR,768
Const ED_FURTHER,1280
Const ED_VERY_FAR,2048

// Flags
current
hint_all
hint_hidden
hint_visible
area_all
area_hidden
area_visible
cover
backaway

// Goal flags
safe
hint_group
from_target
hint_face
use_node
nearest
move_from_target
random
once
area_group
</code></pre>
<h1>Syntax</h1>
<p><code class="language-js">FreeMovementParams [flag],[distance min],[distance max],[goalflag1],[goalflag2],[goalflag3], ..</code>
<h1>Example</h1>
<pre><code class="language-js">
// This will allow the NPC to move everywhere in it's area group
FreeMovementParams area_all,-1,-1,area_group

// This will restrict the NPC to move inside hint groups only
FreeMovementParams hint_all,-1,-1,hint_group

// This will make the NPC move to a hint group or node, only once
FreeMovementParams hint_all,ED_MIDDLE,ED_VERY_FAR,hint_group,hint_face,use_node,once

// This will force the NPC to be really close to it's target
FreeMovementParams area_all,0,ED_VERY_CLOSE,from_target

// This however will make the NPC go away from it's target as far as possible
FreeMovementParams area_all,ED_VERY_FAR,ED_VERY_FAR,move_from_target
</code></pre>