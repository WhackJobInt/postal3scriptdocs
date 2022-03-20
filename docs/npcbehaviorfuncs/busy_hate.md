# Emotion Functions

## Busy
<p>Forces NPC to be Busy.</p>
<p>Equivalent to <code>SetAttr "busy [1/0]"</code>, so it's somewhat unused.</p>
<h2>Syntax</h2>
<p><code class="language-js">Busy [true/false]</code></p>

<br>
## Hate
<p>Forces Hate towards a target object.</p>

<ul>
<div class="admonition note">
<p class="admonition-title">Note</p>
<li>NPC's Squad members will forget or hate the same target object.</li>
</div>
</ul>

<h2>Syntax</h2>
<p><code class="language-js">Hate [true/false],[normal/guard/assault/retreat/roundup]:[param]</code> -- Tactical variant and param only works with Military NPCs
<h1>Example</h1>
<pre><code class="language-js">
// Will only work with Military NPCs
pt_hateGuard
{
	actions
	{
		Hate true,guard:1500
	}
}

// Will work with normal NPCs and including Military ones too
pt_hateThem
{
	actions
	{
		Hate true
	}
}
</code></pre>