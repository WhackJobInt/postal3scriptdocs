# Follow and PlayerFriendly

## Follow

Forces NPC to follow it's target object

!!! warning "Broken Feature"
	This function can only be enabled or disabled, <code>walk</code> or <code>run</code> will **not do anything**.  
	If you want to make an NPC follow something by walking, [set it's act pack](../movementfuncs/setactpack.md) instead.

<h2>Syntax</h2>
<p><code class="language-js">Follow [true/false]</code></p>
<p><code class="language-js">Follow [walk/run],[distance]</code></p>

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

<br>
## PlayerFriendly
<p>Unused Postal3Script function
<p>Sets NPC to never hit the Player with bullets, aka. Friendly Fire
<h2>Syntax</h2>
<p><code class="language-js">PlayerFriendly [true/false]</code>