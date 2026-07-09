## TargetCallersTarget

<p>Targets the caller's target.</p>

<div class="admonition warning">
<p class="admonition-title">Postal III Ultrapatch+Angel v1.3.0+ Feature</p>
<p>The following function will only work in <b>Postal III Ultrapatch+Angel v1.3.0 or higher</b>.</p>
</div>

<h1>Syntax</h1>
<p><code>TargetCallersTarget 1</code> -- Targets the caller's target.</p>

<h1>Example</h1>
<pre><code class="language-js">
// Targets the caller's target, then goes into a different pattern.
pt_default
{
	actions
	{
		TargetCallersTarget 1
		Pattern pt_addtargettoenemy
	}
}
</code></pre>