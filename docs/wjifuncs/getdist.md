## GetDist

<p>Gets the distance between two objects, and puts it's value into an attribute.</p>

<div class="admonition warning">
<p class="admonition-title">Catharsis Reborn Feature</p>
<p>The following function will only work in <b>Catharsis Reborn</b>.</p>
</div>

<h1>Syntax</h1>

`GetDist "<attribute>,<Object1>,<Object2>"` -- Gets the distance between `<Object1>` and `<Object2>`, and puts it's value into `<attribute>`.</p>

<h1>Example</h1>

```
// Gets the distance between the target and the player
xpt_distCheck
{
	actions
	{
		GetDist "distToPlayer,Object:target,Object:player"
		// Target seems to be very close to the player...
		IfAttr "distToPlayer < 100 Block begin"
			Pattern pt_playerclose
		Block end
	}
}
```