#- Snatch
<p>Snatches onto an NPC
<p>* Can be used only by Animals
<p>* Must have a target object
<h2>Syntax</h2>
<p><code class="language-js">Snatch [true/false], [attachment]</code>
<pre><code class="language-js">
// Attachments	// Where to snatch
fucking_monkey 	= head
snatch0			= left foot
snatch1			= right foot
snatch2			= left hand
snatch3			= right hand
</code></pre>
<h1>Example</h1>
<pre><code class="language-js">
// from ai_mission_mli.p3s
pt_attack
{
	actions
	{
		Snatch true,fucking_monkey
		Wait 5:2
		Snatch false
		State st_start
	}
}
</code></pre>

<br><br><h1>- Unsnatch</h1>
<p>Unused Postal3Script function
<p>Unsnatches from an NPC
<p>* Must have a target object
<h2>Syntax</h2>
<p><code class="language-js">Unsnatch 1</code>