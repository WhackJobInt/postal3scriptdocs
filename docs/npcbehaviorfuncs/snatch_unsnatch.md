# Snatching Functions

## Snatch

Snatches onto an NPC

<ul>
<div class="admonition note">
<p class="admonition-title">Note</p>
<li>Can only be used by Animals</li>
<p>
<li>Must have a target object</li>
</div>
</ul>

<h2>Syntax</h2>
<p><code class="language-js">Snatch [true/false],[attachment]</code></p>
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

<br>
## Unsnatch

Unused Postal3Script function

Unsnatches from an NPC

<div class="admonition note">
<p class="admonition-title">Note</p>
<li>Must have a target object</li>
</div>

<h2>Syntax</h2>
<p><code class="language-js">Unsnatch 1</code>