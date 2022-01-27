#- CheckTarget
<p>Checks if target is visible
<h1>Syntax</h1>
<p><code class="language-js">CheckTarget 1</code> -- Target is checked
<h1>Technical Details</h1>
<p>If target is busy and exists, an event called "OnTargetReset" will be fired with the target being the caller, and the NPC that called CheckTarget will get their target nulled out.
<p>If that check fails, NPC will forget their target, look for potential targets, and fire "OnVisible" event with the target being the caller
<p>If even that fails, the event "OnTargetReset" will be fired on the NPC.
<h1>Example</h1>
<pre><code class="language-js">
// from ai_mission_pdb.p3s
pt_move
{
	actions
	{
		MoveToTarget walk,0
		Wait 2:5
		Say ZOMB_MOAN,ZOMB_CURSE,0
		CheckTarget 1
		Repeat 1
	}
	events
	{
		OnVisible "Pattern pt_barf"
	}
}
</code></pre>

<br><br><h1>- CheckLOS</h1>
<p>Checks if target is able to see the caller
<h1>Syntax</h1>
<p><code class="language-js">CheckLOS 1</code> -- Checks target's line of sight
<h1>Technical Details</h1>
<p>Fires event "OnLOS" if target is able to see the caller
<h1>Example</h1>
<pre><code class="language-js">
// from ai_mission_pm2.p3s
pt_loop
{
	actions
	{
		// Target can't see us, perfect, kill ourselves
		IfAttr "Timer:tKill <= 0 Npc kill"
		CheckLOS 1
		Repeat 1
	}
	events
	{
		// The timer's counter will be reset to 3 everytime the target is able to see
		OnLOS "Timer tKill,3"
	}
}
</code></pre>