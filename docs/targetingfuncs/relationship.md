# Relationship
<p>Sets NPC's friendliness towards objects
<h1>Syntax</h1>
<p>[priority] = Relative importance of this relationship (higher numbers mean more important)
<p><code class="language-js">Relationship target,[neutral/enemy/fear],[priority]</code>
<p><code class="language-js">Relationship caller,[neutral/enemy/fear],[priority]</code>
<p><code class="language-js">Relationship all_enemy,[neutral/enemy/fear],[priority]</code>
<p><code class="language-js">Relationship all_fear,[neutral/enemy/fear],[priority]</code>
<p><code class="language-js">Relationship all_neutral,[neutral/enemy/fear],[priority]</code>
<h1>Example</h1>
<pre><code class="language-js">
// (from ai_mission_bdk.p3s)
// You think you can take Krotchy down?!
xpt_firstrun
{
	actions
	{
		TargetEntByName "npc_krotchy"
		TargetToMem msLEADER
		
		TargetPlayer 1
		Relationship target,enemy,1
		SetSquad krotchy_squad
		ResetTarget 1
		RemoveAttr FirstRun
		
		State st_start
	}
}
</code></pre>