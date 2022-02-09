# String
<p>A special object for checking for text in different objects.</p>
<p>Check out <a href="../../objects/name">Name</a> and <a href="../../objects/voiceprefix">VoicePrefix</a> for possible String object checks.


<h1>Example</h1>
<pre><code class="language-js">
// Checking for an NPC's name (this is set in Hammer)
IfAttr "Name:self == String:npc_ninja2 TargetEntByName npc_ninja1"
// or
IfAttr "ea_name == String:npc_ninja2 TargetEntByName npc_ninja1"

// Checking for NPC's voice prefix
IfAttr "VoicePrefix:self == String:PF Say WF_SCREAM,2"
</code></pre>