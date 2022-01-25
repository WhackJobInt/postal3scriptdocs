# VoicePrefix
<p>Check the prefix of an NPC's voice
<p>The voice prefix can be found in the related NPC's sentence script located in "Postal III\p3\scripts\Sentences". Everything
before the underscore is the voice prefix.
<pre><code class="language-js">
// If we don't use the "whore" npc voice prefix
// say a "sentence" type voice line about a cop going crazy
// (whore npc's don't have any lines recorded for this scenario)
IfAttr "VoicePrefix:self != String:WHR Say MADCOP"
</code></pre>