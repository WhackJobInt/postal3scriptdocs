# Various Targeting Functions

## AssistTarget

Sets current target/enemy as target object internally for script.

<h1>Syntax</h1>
<p><code class="language-js">AssistTarget 1</code> -- Sets current target/enemy as target object internally</p>
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

<br>
## AssistEnemy

Unused Postal3Script function

Sets current target's enemy as target

<h1>Syntax</h1>
<p><code class="language-js">AssistEnemy 1</code> -- Sets current target's enemy as target</p>

<br>
## ArrestTarget
Unused Postal3Script function

Arrests the target.

<ul>
<div class="admonition note">
<p class="admonition-title">Note</p>
<li>Target object must be the Player</li>
<li>Only works for <code>p3_npc_cop</code> NPCs </li>
</div>
</ul>

<h1>Syntax</h1>
<p><code class="language-js">ArrestTarget true</code> -- Target is arrested</p>
<p><code class="language-js">ArrestTarget false</code> -- Target is no arrested</p>
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

<br>
## BusyTarget

Unused Postal3Script function

Sets target's busy state internally

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Can target self</p>
</div>

<h1>Syntax</h1>
<p><code class="language-js">BusyTarget true</code> -- Target is busy</p>
<p><code class="language-js">BusyTarget false</code> -- Target is no longer busy</p>
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