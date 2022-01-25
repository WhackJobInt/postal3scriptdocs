# VoicePrefix
<p>Check the prefix of an NPC's voice
<p>Possible Prefixes are from 'scripts/Sentences' folder
<pre><code class="language-js">
// If we don't use the "whore" npc voice prefix
// say a "sentence" type voice line about a cop going crazy
// (whore npc's don't have any lines recorded for this scenario)
IfAttr "VoicePrefix:self != String:WHR Say MADCOP"
</code></pre>