#- Wait
<p>A Timer to wait before execution
<h1>Syntax</h1>
<p><code class="language-js">Wait [float]</code> -- Wait before executing
<h1>Example</h1>
<pre><code class="language-js">
// from ai_mission_aa.p3s
st_tank
{
	Group Neutral
	Patterns
	{
		pt_default
		{
			actions
			{
				PlayVideo aa_2,1,1
				
				// Wait this much to not spawn the Boss immediately
				Wait 1.2
				
				MissionLog add_primary,tank,#P3_AA_LOG3
				EntFireInput muzak.battle,FadeIn:1
				EntFireInput hugo_spawner,Enable
				EntFireInput spawner_invaders,Enable
				ShowMessage #P3_AA_MSG3
			}
		}
	}
}
</code></pre>

<br><br><h1>- WaitForEnd</h1>
<p>Wait for an ongoing activity before execution
<p>Mostly used for sequences
<h1>Syntax</h1>
<p><code class="language-js">WaitForEnd 1</code> -- Wait for ending before execution
<h1>Example</h1>
<pre><code class="language-js">
// from ai_mission_cw.p3s
st_opencage_02
{
	Group Alert
	Patterns
	{
		pt_default
		{
			actions
			{
				Weapon disarm
				Sequence seq.env_checking
				
				// Wait for "env_checking" animation to end
				WaitForEnd 1
				
				Weapon arm
				
				EntFireInput "door_dogs_02,OpenAwayFrom:!activator"
				State st_start
			}
		}
	}
}
</code></pre>

<br><br><h1>- Repeat</h1>
<p>Repeats a pattern every defined second(s)
<h1>Syntax</h1>
<p><code class="language-js">Repeat [float]</code> -- Repeat every [float] seconds
<h1>Example</h1>
<pre><code class="language-js">
// This will create a loop in pt_loop endlessly, unless we exit from out it
st_start
{
	Group Neutral
	Patterns
	{
		pt_default
		{
			actions
			{
				PlayerKarma hide
				MissionLog disable
				Pattern pt_loop
			}
		}
		
		pt_loop
		{
			actions
			{
				Repeat 2
			}
		}
	}
}
</code></pre>