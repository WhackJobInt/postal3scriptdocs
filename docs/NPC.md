# NPC
<p>Kills current NPC executed from script
<h1>Syntax</h1>
<p><code class="language-js">NPC kill, [fade out time]</code> -- Kills NPC with time waiting for fading out
<h1>Example</h1>
<pre><code class="language-js">
// This will kill the NPC after 1 second after execution
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
		NPC kill, 2.5
	}
}
</code></pre>