#- Busy
<p>Forces NPC to be Busy.
<p>Equivalent to <code class="language-js">SetAttr "busy [1/0]"</code>, so it's somewhat unused.
<h2>Syntax</h2>
<p><code class="language-js">Busy [true/false]</code>

<br><br><h1>- Fear</h1>
<p>Unused Postal3Script function.
<p>Turns on or off NPC's ability to fear.
<p>Will not do anything
<h2>Syntax</h2>
<p><code class="language-js">Fear [true/false]</code>

<br><br><h1>- Hate</h1>
<p>Forces Hate towards a target object.
<p>* Squad members will forget or hate the target object.
<p>* Doesn't work with Player as the target object.
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