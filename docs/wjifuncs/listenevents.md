## ListenEvents

<p>Makes an entity listen for game events.</p>

<div class="admonition warning">
<p class="admonition-title">Catharsis Reborn Feature</p>
<p>The following function will only work in <b>Catharsis Reborn</b>.</p>
</div>

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Uses events from <code>ModEvents.res</code></p>
</div>

<h1>Syntax</h1>
<p><code>ListenEvents 1</code> -- Turns on or off to listen for game events.</p>
<p>Will call <code>OnEvent_[eventname]</code> P3S events dynamically.</p>

<h1>Example</h1>
<pre><code class="language-js">
behavior
{
	name bh_npc_myentity
	inherited bh_military_new
	States
	{
		st_init
		{
			Group Neutral
			Patterns
			{
				pt_default
				{
					actions
					{
						ListenEvents 1
						AvoidProhibitedArea false
						ExecutePattern "bh_military_new:st_init.pt_default"
					}
				}
			}
		}
	}
	events
	{
		OnEvent_p3_player_hurt "PrintAttr OnEvent_p3_player_hurt"
		OnEvent_p3_npc_hurt "PrintAttr OnEvent_p3_npc_hurt"
		OnEvent_player_death "PrintAttr OnEvent_player_death"
	}
}
</code></pre>