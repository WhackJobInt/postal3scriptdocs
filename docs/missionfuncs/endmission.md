# EndMission
<p>Ends the level, and proceeds to the next level (if possible)

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Equivalent to <code>p3_end_mission</code> console command
</div>


<h1>Example</h1>
<pre><code class="language-js">
// from ai_mission_daveland.p3s
st_end
{
	Group Neutral
	Patterns
	{
		pt_default
		{
			actions
			{
				EntFireInput lpp,Say:ENDEVENTINSANE
				Wait 1
				EntFireInput muzak.mission,FadeOut:1
				MissionLog done,escape
				EndMission 1
				
				// Alternative way to end a mission
				EntFireInput "pcc,Command:p3_end_mission"
			}
		}
	}
}
</code></pre>