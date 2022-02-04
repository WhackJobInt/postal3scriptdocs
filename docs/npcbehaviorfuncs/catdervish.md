# CatDervish

Forces NPC to enter into Dervish mode

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>NPC must be a Cat</p>
</div>

<h2>Syntax</h2>
<p><code class="language-js">CatDervish [true/false],[time]</code> -- Sets Dervish mode, and optionally a timer
<h1>Example</h1>
<pre><code class="language-js">
// (from ai_npc_animal.p3s)
st_deactivate
{
	Group Alert
	Patterns
	{
		pt_default
		{
			actions
			{
				CatDervish false
				SetAttr "ea_takeable 0"
				ExecutePattern bh_base:st_deactivate.pt_default
			}
		}
	}
}
</code></pre>