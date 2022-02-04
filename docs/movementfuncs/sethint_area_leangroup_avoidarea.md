# Hint Group Functions

## SetHintGroup

Sets NPC's hint group

<h1>Syntax</h1>
<p><code class="language-js">SetHintGroup [hint group1],[hint group2],[hint group3], ..</code> -- Sets hint groups for NPC</p>
<h1>Example</h1>
<pre><code class="language-js">
// from ai_mission_pw.p3s
xpt_SetHintGroup
{
	actions
	{
		SetAttr "rand 0"
		ChangeAttr "rand 0:3"
		IfAttr "rand == 0 SetHintGroup wish_fun_droch"
		IfAttr "rand == 1 SetHintGroup wish_fun_drink"
		IfAttr "rand == 2 SetHintGroup wish_fun_watch"
		IfAttr "rand == 3 SetHintGroup wish_fun_strip"
		RemoveAttr rand
	}
}
</code></pre>

<br>
## SetAreaGroup

Sets NPC's area group(s)

<h1>Syntax</h1>
<p><code class="language-js">SetAreaGroup [Group1]:[walkable],[Group2]:[walkable],[Group3]:[walkable], ..</code> -- Sets area groups for NPC</p>
<p>:[walkable] is optional</p>
<p><code class="language-js">SetAreaGroup AG_DEFAULT</code> -- Resets NPC's area group</p>

<br>
## SetLeanGroup

Sets NPC's lean group(s)

<div class="admonition tip">
<p class="admonition-title">Tip</p>
<p>Decompile <code>dcr.bsp</code> to analyze how a Lean group works.</p>
</div>

<h1>Syntax</h1>
<p><code class="language-js">SetLeanGroup [Group1],[Group2],[Group3], ..</code> -- Sets lean groups for NPC</p>

<br>
## AvoidProhibitedArea

Sets NPC to avoid prohibited areas

<h1>Syntax</h1>
<p><code class="language-js">AvoidProhibitedArea [boolean]</code></p>
<pre><code class="language-js">
// (From ai_freeroaming.p3s)
// this AI will refuse to walk out from it's set area group
behavior
{
	name bh_mexico_roam_police
	inherited bh_police
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
						ExecutePattern bh_base:st_init.pt_default
						
						SetAreaGroup AG_DEFAULT,AG_border
						AvoidProhibitedArea true 
					}
				}
			}
		}
	}
}
</code></pre>