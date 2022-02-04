# Deprecated Pattern Functions

<div class="admonition warning">
<p class="admonition-title">Warning</p>
<p>It's not recommended to use these functions. They are only here for documenting purposes.</p>
<p>Use functions from <a href="../../statefuncs/func_state_pattern_executepattern">THIS</a> page instead.</p>
</div>
<br>

## StoreActivityPattern

Unused Postal3Script function

Stores an Activity Pattern

<h1>Syntax</h1>
<p><code class="language-js">StoreActivityPattern [string]</code> -- Stores a pattern from current state</p>
<h1>Example</h1>
<pre><code class="language-js">
st_mycustomstate
{
	group Neutral
	patterns
	{
		pt_default
		{
			actions
			{
				// This will store pt_ketchup from the current state
				StoreActivityPattern pt_ketchup
			}
		}
		
		pt_ketchup
		{
			actions
			{
				ChangeAttr "Ketchup +1"
			}
		}
	}
}
</code></pre>

<br>
## ExecuteActivityPattern

Unused Postal3Script function

Executes Activity Pattern

<h1>Syntax</h1>
<p><code class="language-js">ExecuteActivityPattern true</code> -- Executes currently stored pattern</p>

<br>
## ClearActivityPattern

Unused Postal3Script function

Clears Activity Pattern

<h1>Syntax</h1>
<p><code class="language-js">ClearActivityPattern true</code> -- Clears currently stored pattern</p>