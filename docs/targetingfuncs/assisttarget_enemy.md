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