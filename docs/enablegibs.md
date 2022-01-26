# EnableGibs
<p>Unused Postal3Script function
<p>Enables or Disables gibbing of an NPC
<h1>Syntax</h1>
<p><code class="language-js">EnableGibs true</code> -- Enables gibbing (default)
<p><code class="language-js">EnableGibs false</code> -- Disables gibbing
<h1>Example</h1>
<pre><code class="language-js">
// from ai_st6_missions.p3s
// This will force Uwe Boll to never gib on death/or when injured when he's spawned into the game
st_init
{
	Group Neutral
	patterns
	{
		pt_default
		{
			actions
			{
				EnableGibs false
				SetAttr "UweTask UWE_WAITFORMISSION"
				SetAttr "ea_dmg_absorb 60"
				Pattern bh_human:st_init.pt_default
			}
		}
	}
}
</code></pre>