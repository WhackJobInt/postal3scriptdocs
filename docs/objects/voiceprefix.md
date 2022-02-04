# VoicePrefix

The prefix of an NPC's voice.

<p>The voice prefix can be found in the related NPC's sentence data script entry located in</p>

<code>.\Postal III\p3\scripts\sentences_data.txt</code>

<p></p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Everything before the underscore is considered the voice prefix.</p>
</div>

<h1>Syntax</h1>
<p><code class="language-js">VoicePrefix:[object]</code> -- Returns the voice prefix of the specified object
<pre><code class="language-js">
// If we don't use the "whore" npc voice prefix
// say a "sentence" type voice line about a cop going crazy
// (whore npc's don't have any lines recorded for this scenario)
IfAttr "VoicePrefix:self != String:WHR Say MADCOP"
</code></pre>