## TargetCallersTarget

<p>Targets the caller's target.</p>

<div class="admonition warning">
<p class="admonition-title">Catharsis Reborn Feature</p>
<p>The following function will only work in <b>Catharsis Reborn</b>.</p>
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