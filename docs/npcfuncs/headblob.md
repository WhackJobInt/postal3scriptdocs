# Headblob
<p>Spawns an effect above an NPC's head

<ul>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Headblobs are defined in <code>p3/scripts/p3_headblobs.txt</code>, and uses particle effects.</p>
Pre-defined Headblobs:
<li><code>Stars</code></li>
<li><code>Zzzz</code></li>
<li><code>HappyCat</code></li>
<li><code>Attention</code></li>
<li><code>Arrest</code></li>
</div>
</ul>

<h2>Syntax</h2>
<p><code class="language-js">Headblob [integer],[name]</code>

<div class="admonition warning">
<p class="admonition-title">Warning</p>
<p>The numbers don't do anything, it is however still needed because <code>Headblob</code> only accepts 2 parameters.</p>
</div>

<h1>Example</h1>
<pre><code class="language-js">
// Example
pt_eat
{
	actions
	{
		Sequence an_idle_eat
		Wait 2
		Wait 0:2
		
		Headblob 1,HappyCat
		
		Pattern pt_end
	}
}
</code></pre>