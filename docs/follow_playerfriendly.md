#- Follow
<p>Forces NPC to follow it's target object
<h2>Syntax</h2>
<p><code class="language-js">Follow [true/false]</code>
<p><code class="language-js">Follow [walk/run],[distance]</code>
<h1>Example</h1>
<pre><code class="language-js">
// (from ai_st11_urza.p3s)
pt_default
{
	actions 
	{
		Sequence arrest_me,2
		WaitForEnd 1
		RemoveAttr "ArrestWait"
		TargetToMem 5
		FreeMovement false
		Follow walk,3
		Pattern pt_loop
	}
}
</code></pre>

<br><br><h1>- PlayerFriendly</h1>
<p>Unused Postal3Script function
<p>Sets NPC to never hit the Player with bullets, aka. Friendly Fire
<h2>Syntax</h2>
<p><code class="language-js">PlayerFriendly [true/false]</code>