# Ignore
<p>Unused Postal3Script Object</p>
<p>Checks if an object is ignored.</p>

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Can only be used with <a href="../../targetingfuncs/reset_ignore_settarget/#ignoretarget">IgnoreTarget</a> beforehand.</p>
</div>

<div class="admonition error">
<p class="admonition-title">Bug</p>
<p>Using against corpses doesn't work, even though <code>IgnoreTarget</code> has proper coding for it.</p>
</div>

<h1>Syntax</h1>
<p><code class="language-js">Ignore:[object type]</code> -- Checks if the type is already ignored or not</p>

</code></pre>
<h1>Example</h1>
<pre><code class="language-js">
st_somestate
{
	group Neutral
	patterns 
	{
		pt_default
		{
			actions
			{
				// Target was already being ignored!
                IfAttr "Ignore:target == 1 Block begin"
					ResetTarget 1
					Pattern pt_end
				Block end
				
				// Not ignored!
				IfAttr "Ignore:target == 0 Block begin"
					IgnoreTarget 20
					ResetTarget 1
					Pattern pt_ignored
				Block end
			}
		}
	}
}
</code></pre>