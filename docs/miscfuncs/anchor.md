# Anchor functions

## Anchor
<p>Spawns an invisible entity, and sets the pointer to it.</p>

<h1>Syntax</h1>
<p><code class="language-js">Anchor true,[type]</code> -- Spawns Anchor, [type] is optional</p>
<p><code class="language-js">Anchor false,[type]</code> -- Removes Anchor from the game, [type] is optional</p>

<p></p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p><code>[type]</code> is an object type, like <code>target</code>, <code>caller</code>, <code>owner</code>, ...</p>
<p>If <code>[type]</code> is not specified, it will execute on the current entity the script being ran from.</p>
<p>If <code>[type]</code> is specified and it's not <code>self</code>, it will save the script executioner's location to <code>[type]</code>.</p>
</div>

<h1>Example</h1>
<pre><code class="language-js">
// This example shows you how to make an NPC run to it's target, and back to it's last known location.
st_somestate
{
	Group Alert
	Patterns
	{
		pt_default
		{
			actions
			{
				TargetCaller 1
				// Save this location!
				Anchor true
				// Run to my current target!
				MoveToTarget run,1
				
				Pattern pt_loop
			}
		}
		
		pt_loop
		{
			actions
			{
				IfAttr "Object:target != Object:NULL Block begin"
					// We pretty much reached our target
					IfAttr "Object:target != Object:anchor Block begin"
						IfAttr "DistTo:target <= 52 Pattern pt_goback"
					Block end
					
					// We are targeting our anchor!
					IfAttr "Object:target == Object:anchor Block begin"
						IfAttr "DistTo:target <= 52 Block begin"
							// We pretty much reached our target
							FreeMovement walk,reset
							State st_start
						Block end
					Block end
				Block end
				
				Repeat 0
			}
		}
		
		pt_goback
		{
			actions
			{
				// Target our Anchor we saved earlier in pt_default!
				TargetAnchor 1
				// Run to it!
				MoveToTarget run,1
				
				Pattern pt_loop
			}
		}
	}
}
</code></pre>

<br>
## TargetAnchor
<p>Sets internal target to entity's saved Anchor, if there's any.</p>

<h1>Syntax</h1>
<p><code class="language-js">TargetAnchor 1</code> -- Sets internal target to Anchor</p>

<p></p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>To get an entity's Anchor other than the script executioner's, you will have to use <a href="../../targetingfuncs/reset_ignore_settarget/#settarget">SetTarget</a>.</p>
</div>