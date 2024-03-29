# Various Target functions

## ResetTarget

Resets target object.

<h2>Syntax</h2>
<p><code class="language-js">ResetTarget 1</code> -- Resets target object</p>
<h1>Example</h1>
<pre><code class="language-js">
// This will set the Player, and an object from memory as enemy
xpt_IHateEveryone
{
	actions
	{
		TargetFromMem 6
		Relationship target, enemy, 1
		
		ResetTarget 1
		
		TargetPlayer 1
		Relationship target, enemy, 2
		
		ResetTarget 1
	}
}
</code></pre>

<br>
## IgnoreTarget

Ignores a target object for a specified time.

<h1>Syntax</h1>
<p><code class="language-js">IgnoreTarget [integer]</code> -- NPC will not know this object exists for 5 seconds</p>
<p><code class="language-js">IgnoreTarget [integer]:[integer]</code> -- NPC will not know this object exists for a randomized time</p>
<h1>Example</h1>
<pre><code class="language-js">
pt_end
{
	actions
	{
		IgnoreTarget 20
		ResetTarget 1
		
		State st_start
	}
}
</code></pre>

<br>
## SetTarget

Sets target objects for an object

<h1>Syntax</h1>
<p><code class="language-js">SetTarget "[object].Object:target Object:[object]"</code> -- Sets the object's target object from the caller's object</p>
<p><code class="language-js">SetTarget "Object:self target.Object:slot#[memory slot]"</code> -- Sets our target from a target's memory slot</p>
<h1>Example</h1>
<pre><code class="language-js">
// This will set our target's target object ourself
SetTarget "target.Object:target Object:self"

// This will set our target's target object our caller
SetTarget "target.Object:target Object:caller"

// This will set the caller's target object ourself
SetTarget "caller.Object:target Object:self"

// This will set our target object from our current target's memory slot
SetTarget "Object:self target.Object:slot#6"
</code></pre>