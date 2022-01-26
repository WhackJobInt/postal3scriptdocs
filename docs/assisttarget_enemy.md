#- AssistTarget
<p>Sets current target as target internally
<h1>Syntax</h1>
<p><code class="language-js">AssistTarget 1</code> -- Sets current target as target internally
<h1>Example</h1>
<pre><code class="language-js">
pt_npcdead
{
	actions
	{
		IfAttr "ea_Manner == Manner:JusticeMan Block begin"
			TargetCaller 1
			Weapon select,ranged
			AssistTarget 1
			Relationship target,enemy
			State st_start
		Block end
	}
}
</code></pre>

<br><br><h1>- AssistEnemy</h1>
<p>Unused Postal3Script function
<p>Sets current target's enemy as target
<h1>Syntax</h1>
<p><code class="language-js">AssistEnemy 1</code> -- Sets current target's enemy as target

<br><br><h1>- ArrestTarget</h1>
<p>Unused Postal3Script function
<p>Arrests the target, only works for Player
<p>Only works for "p3_npc_cop" NPCs 
<h1>Syntax</h1>
<p><code class="language-js">ArrestTarget true</code> -- Target is arrested
<p><code class="language-js">ArrestTarget false</code> -- Target is no arrested
<h1>Example</h1>
<pre><code class="language-js">
// from ai_st5_temp.p3s
st_test_arrest
{
	group Neutral
	patterns
	{
		pt_arrest
		{
			actions
			{
				FreeMovement false
				TargetPlayer 1
				ArrestTarget true
				Wait 30
				ArrestTarget false
				State st_start
			}
		}
	}
}
</code></pre>

<br><br><h1>- BusyTarget</h1>
<p>Unused Postal3Script function
<p>Sets target's busy state internally
<p>Can target self
<h1>Syntax</h1>
<p><code class="language-js">BusyTarget true</code> -- Target is busy
<p><code class="language-js">BusyTarget false</code> -- Target is no longer busy
<h1>Example</h1>
<pre><code class="language-js">
// from ai_st11_urza.p3s
st_p3_buy_cash
{
	group Neutral
	patterns
	{
		pt_default
		{
			actions
			{	
				BusyTarget true	// SELLER IS BUSY
				targetToMem 2	// mem2 is seller
				targetFromMem 1	// target is thing
				FreeMovement false
				Sequence itm_discard
				WaitForEnd 1
				targetFromMem 2	//target is seller
				FireEvent NeedBuy
			}
		}
	}
}
</code></pre>

<br><br><h1>- CheckTarget</h1>
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