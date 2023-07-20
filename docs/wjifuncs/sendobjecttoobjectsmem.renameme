## SendObjectToObjectsMem

<p>Sends an Object to the object's memory slot.</p>

<div class="admonition warning">
<p class="admonition-title">Catharsis Reborn Feature</p>
<p>The following function will only work in <b>Catharsis Reborn</b>.</p>
</div>

<h1>Syntax</h1>
`SendObjectToObjectsMem "Object:<obj_send>,Object:<obj_receiver>,<memslot>"` -- Sends `Object:<obj_send>` to `Object:<obj_receiver>`'s `<memslot>` mem slot.</p>

<h1>Example</h1>
```
// Example code from Dog Toy
pt_thrown
{
	actions
	{
		SetAttr "cr_thrown 1"
		// Caller will now be in memory slot DOGTOY_THROWER
		SendObjectToObjectsMem "Object:caller,Object:self,DOGTOY_THROWER"
		AreaEvent ToyThrown,DOGTOY_THROWN_RADIUS,StrayDog
		Wait DOGTOY_THROWN_IDLE_WAIT
		Pattern pt_loop
	}
}
```