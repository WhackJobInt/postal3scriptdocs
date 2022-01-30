<h1>Note: It's not advised to use these functions</h1>
<h1>- StoreActivityPattern</h1>
<p>Unused Postal3Script function
<p>Stores an Activity Pattern
<h1>Syntax</h1>
<p><code class="language-js">StoreActivityPattern [string]</code> -- Stores a pattern from current state
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

<br><h1>- ExecuteActivityPattern</h1>
<p>Unused Postal3Script function
<p>Executes Activity Pattern
<h1>Syntax</h1>
<p><code class="language-js">ExecuteActivityPattern true</code> -- Executes currently stored pattern

<br><h1>- ClearActivityPattern</h1>
<p>Unused Postal3Script function
<p>Clears Activity Pattern
<h1>Syntax</h1>
<p><code class="language-js">ClearActivityPattern true</code> -- Clears currently stored pattern