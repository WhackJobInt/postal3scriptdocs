#- State
<p>Exits from current state, and enters a new state
<h1>Syntax</h1>
<p><code class="language-js">State [state name]</code> -- Sets the new state
<h1>Example</h1>
<pre><code class="language-js">
// On start after 5 seconds it will exit from st_start and enter st_new_start, and back forth
st_start
{
	Group Neutral
	Patterns
	{
		pt_default
		{
			actions
			{
				Wait 5
				State st_new_start
			}
		}
	}
}

st_new_start
{
	Group Neutral
	Patterns
	{
		pt_default
		{
			actions
			{
				Wait 5
				ChangeAttr "TimeTicking +1"
				State st_start
			}
		}
	}
}
</code></pre>

<br><br><h1>- Pattern</h1>
<p>Exits from current pattern from current state, and enters a new pattern in the current state
<h1>Syntax</h1>
<p><code class="language-js">pattern [pattern name]</code> -- Sets the new pattern
<h1>Example</h1>
<pre><code class="language-js">
// State initially enters "pt_default" pattern, but will move to "pt_follow" and will be there endlessly
// from ai_cashmart.p3s
st_idle
{
	Group Neutral
	Patterns
	{
		pt_default
		{
			actions 
			{
				TargetPlayer 1
				Face true
				LookAt 1
				Pattern pt_follow
			}
		}
		
		pt_follow
		{
			actions 
			{
				MoveToTarget true,2
				Wait 10
				Pattern pt_follow
			}
			events
			{
				OnTargetReach "Pattern pt_wait"
			}
		}
		
		pt_wait
		{
			actions 
			{	
				IfAttr "DistTo:target  > 150 Pattern pt_follow"
				Repeat 0.5
			}
		}
	}
}
</code></pre>

<br><br><h1>- ExecutePattern</h1>
<p>Executes a pattern outside of current state
<h1>Syntax</h1>
<p><code class="language-js">ExecutePattern [actor name]:[state name].[pattern name]</code> -- Executes this pattern
<h1>Example</h1>
<pre><code class="language-js">
// This will execute bh_base's st_init's pt_default pattern
ExecutePattern bh_base:st_init.pt_default

// This will execute the state and pattern called "st_onDeath.pt_default" found from the caller's actor
ExecutePattern st_OnDeath.pt_default

// This will execute a pattern that exists in the state the script is currently running from
ExecutePattern .xpt_shout
</code></pre>