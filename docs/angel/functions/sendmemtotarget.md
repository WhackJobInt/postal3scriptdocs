## SendMemToTarget

<p>Sends an object from memory slot to the entity's target.</p>

<div class="admonition warning">
<p class="admonition-title">Postal III Ultrapatch+Angel v1.3.0+ Feature</p>
<p>The following function will only work in <b>Postal III Ultrapatch+Angel v1.3.0 or higher</b>.</p>
</div>

<h1>Syntax</h1>

`SendMemToTarget <memslot>` -- Sets target's target to entity's `<memslot>`.

<h1>Example</h1>

```
// Sends entity's mem slot 7 to the Player, Player's target will be the entity's mem slot 7
xpt_send
{
	actions
	{
		TargetPlayer 1
		IfAttr "Object:slot#7 != Object:NULL SendMemToTarget 7"
	}
}
```