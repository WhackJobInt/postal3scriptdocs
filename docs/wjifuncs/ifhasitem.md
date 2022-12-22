## IfHasItem

<p>Conditional function which checks if object has an inventory item stored.</p>

<div class="admonition warning">
<p class="admonition-title">Catharsis Reborn Feature</p>
<p>The following function will only work in <b>Catharsis Reborn</b>.</p>
</div>

<h1>Syntax</h1>
`IfHasItem "Object:<obj> <itemid> <action>` -- Checks if `Object:<obj>` has `<itemid>` stored in their inventory.</p>

<h1>Example</h1>
```
// Example code
xpt_checkVarious
{
	actions
	{
		IfHasItem "Object:self ITM_BONE Pattern pt_chomp"

		IfHasItem "Object:player ITM_PIZZA Block begin"
			Pattern pt_givemeallyourfoodsucker
		Block end
	}
}
```