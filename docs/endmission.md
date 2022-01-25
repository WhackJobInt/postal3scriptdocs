# EndMission
<p>Ends the level, and proceeds to the next level (if possible)
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
			}
		}
	}
}
</code></pre>