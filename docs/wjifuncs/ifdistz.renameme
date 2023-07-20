## IfDistZ

<p>Conditional function which checks the height difference between the entity and target.</p>

<div class="admonition warning">
<p class="admonition-title">Catharsis Reborn Feature</p>
<p>The following function will only work in <b>Catharsis Reborn</b>.</p>
</div>

<h1>Syntax</h1>
`IfDistZ "+- Object:<obj> <operator> <value> <action>"` -- Compares calculated height difference without any modifications. (default, and recommended if you want to know if target is over or under you)</p>
`IfDistZ "++ Object:<obj> <operator> <value> <action>"` -- Turns calculated height difference into positive to check against that, if it's negative.</p>
`IfDistZ "-- Object:<obj> <operator> <value> <action>"` -- Turns calculated height difference into negative to check against that, if it's positive</p>

<h1>Example</h1>
```
// Example code which checks if the target is over, under, or if it doesn't matter, but the difference is still high
xpt_checkHeight
{
	actions
	{
		IfDistZ "+- Object:target < -12 Pattern pt_overme"
		IfDistZ "+- Object:target > 12 Pattern pt_underme"
		IfDistZ "++ Object:player > 12 Pattern pt_deep"
	}
}
```