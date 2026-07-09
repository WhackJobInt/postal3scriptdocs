## SendObjectToTargetsMem

<p>Sends an Object to the target's memory slot.</p>

<div class="admonition warning">
<p class="admonition-title">Postal III Ultrapatch+Angel v1.3.0+ Feature</p>
<p>The following function will only work in <b>Postal III Ultrapatch+Angel v1.3.0 or higher</b>.</p>
</div>

<h1>Syntax</h1>
`SendObjectToTargetsMem "Object:<obj>,<memslot>"` -- Sends `Object:<obj>` to the target's `<memslot>` mem slot.</p>

<h1>Example</h1>
```
// Example code of memory sending
xpt_SendMem
{
	actions
	{
		TargetCaller 1
		// Caller's memory slot 7 will now be this entity
		SendObjectToTargetsMem "Object:self,7"
		
		TargetPlayer 1
		// Player's memory slot 7 will now be this entity's caller
		SendObjectToTargetsMem "Object:caller,7"
	}
}
```