# Headblob
<p>Spawns an effect above an NPC's head
<pre><code class="language-js">
// (From p3_headblobs.txt)
// Unused ones without Fx are not listed here
"Stars"			"Stars_headblobs_Fx"
"Zzzz"			"Zzzz_headblobs_Fx"
"HappyCat"		"HappyCat_headblobs_Fx"
"Attention"		"Attention_headblobs_Fx"
"Arrest"		"Arest_headblobs_Fx"
</code></pre>
<h2>Syntax</h2>
<p><code class="language-js">Headblob [integer],[name]</code>
<p>TODO: What does the number mean in front of the name? Maximum number seems to be 5
<h1>Example</h1>
<pre><code class="language-js">
// From ai_npc_animal.p3s
pt_eat
{
	actions
	{
		Sequence an_idle_eat
		EmitSound champ_yummy
		Wait 2
		Wait 0:2
		
		Headblob 1,EmoteSmile
		
		CheckAttr "IsHungry Timer tShit,20"
		RemoveAttr IsHungry
		
		Pattern pt_end
	}
}
</code></pre>