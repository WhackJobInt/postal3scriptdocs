## RandomAttr

<p>Creates or updates an attribute, and randomizes it's value.</p>

<div class="admonition warning">
<p class="admonition-title">Catharsis Reborn Feature</p>
<p>The following function will only work in <b>Catharsis Reborn</b>.</p>
</div>

<h1>Syntax</h1>

`RandomAttr "<attribute>,<min>,<max>"` -- Randomizes the value between `<min>` and `<max>`.</p>
`RandomAttr "<attribute>,<min>"` -- Randomizes the value between `<min>` and 100.</p>
`RandomAttr "<attribute>,<val1>,<val2>,pick"` -- Picks `<val1>` or `<val2>` on a dice roll.</p>

<h1>Example</h1>

```
// Creates and randomizes an attribute, checks if it's higher than 75
xpt_rng
{
	actions
	{
		RandomAttr "RNG,0,100"
		IfAttr "RandomAttr > 75 Block begin"
			Pattern pt_pass
		Block end
	}
}
```