# EmitSound

Plays a sound from an NPC

<ul>
<div class="admonition note">
<p class="admonition-title">Note</p>
<li>Uses names from <code>ai_activities.p3s</code></li>
<p>
<li>Plays on the Voice channel</code></li>
</div>
</ul>

<h2>Syntax</h2>
<p><code class="language-js">EmitSound [name]</code>
<h1>Example</h1>
<pre><code class="language-js">
// (from Catharsis Reborn)
pt_sit
{
	actions
	{
		// Do a purring sound
		EmitSound cat_purr
		Sequence seq.idle_sit,9000
		Wait 10:30
		ResetSequence 1
		State st_start
	}
}
</code></pre>