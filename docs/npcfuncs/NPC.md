# NPC
<p>Removes current NPC executed from script</p>

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Despite the poor naming choice, <code>NPC kill</code> does <b>not</b> actually kill the NPC, but removes it instantly from the game.</p>
</div>

<h1>Syntax</h1>
<p><code class="language-js">NPC kill,[fade out time]</code> -- Kills NPC with time waiting for fading out
<h1>Example</h1>
<pre><code class="language-js">
// This will remove the NPC after 1 second after execution
xpt_KillMyself
{
	actions
	{
		Wait 1
		NPC kill
	}
}

// This will make the NPC fade out in 2.5 seconds
xpt_Disappear
{
	actions
	{
		NPC kill,2.5
	}
}
</code></pre>