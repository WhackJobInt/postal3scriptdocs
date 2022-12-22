## DoFSMArray

<p>Does a single line action for the objects from the entity's array.</p>

<div class="admonition warning">
<p class="admonition-title">Catharsis Reborn Feature</p>
<p>The following function will only work in <b>Catharsis Reborn</b>.</p>
</div>

<h1>Syntax</h1>

`DoFSMArray "Object:<obj> <action>` -- Sets `Object:<obj>` as the target for all of the objects from the array, and handles the action for them.</p>
`DoFSMArray "none <action>` -- Target does not change, and handles the action for objects from the array.</p>

<div class="admonition warning">
<p class="admonition-title">Warning</p>
<p>Does <b>NOT</b> work with <code>Block begin</code> and <code>Block end</code>.</p>
</div>

<h1>Example</h1>
```
// Example code
xpt_fate
{
	actions
	{
		// Player is dead, so we will too.
		IfAttr "player.ea_health <= 0"
			DoFSMArray "none SetAttr ea_health 0"
			SetAttr "ea_health 0"
			Return 1
		Block end
		
		// Not dead? Then follow the player
		DoFSMArray "Object:player Follow true"
		Follow true
	}
}
```