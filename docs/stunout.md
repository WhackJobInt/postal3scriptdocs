# StunOut
<p>Unused Postal3Script function
<p>Stuns an NPC, as if they were shot by a Taser, and collapses
<h1>Syntax</h1>
<p><code class="language-js">StunOut 1</code> -- Stuns NPC
<h1>Example</h1>
<pre><code class="language-js">
// from ai_st1_common.p3s (Line 1124)
// Old Taser code
pt_stunout:ignore_ext_events
{	
	actions 
	{
		Effect 4,Tazer_Hit_Smoke_Fx,pelvis,0,0,-12,-1,true
		RemoveAttr on_tased
		Timer tTASED,0
		IfAttr "MissionCharacter > 0 ExecutePattern ut_set_mis.pt_stunout"
		
		// Stun the NPC
		StunOut 1
		
		Wait 3:6
		Effect 4,reset
		Pattern pt_fakedeath
	}
	events
	{ 
		OnDeath "ExecutePattern .xpt_death"
	}
}
</code></pre>