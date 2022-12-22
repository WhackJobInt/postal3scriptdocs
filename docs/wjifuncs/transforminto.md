## TransformInto

<p>Turns an entity into a scriptifiable entity.</p>

<div class="admonition warning">
<p class="admonition-title">Catharsis Reborn Feature</p>
<p>The following function will only work in <b>Catharsis Reborn</b>.</p>
</div>

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Uses database from <code>cr_spawnitem.txt</code>.</p>
<p>Can't be used on the Player, but it can be used on it's target.</p>
</div>

<h1>Syntax</h1>
`TransformInto target,[name]` -- Turns the target into this scriptified entity.</p>
`TransformInto self,[name]` -- Turns self into this scriptified entity.</p>

<h1>Example</h1>
```{ .lang linenos=true }
// This turns the entity into shit, literally
xpt_dogshit
{
	actions
	{
		TransformInto self,Poop
	}
}
```

<h1>Example (cr_spawnitem.txt)</h1>
```{ .lang linenos=true }
"cr_spawnitem.txt"
{
	"Poop"
	{
		"model"			"models/small_things/shit_01.mdl"	// Path to model
		"type"			"prop_p3_fsmitem"					// This can be 'prop_p3_fsmitem' or 'prop_dynamic'
		"solid"			"0"									// Should it be solid?
		"copytarget"	"0"									// Should it copy the entity's target to the newly created entity?
		"behavior"		"bh_shit"							// The behavior of the new entity
		"manner"		"itmShit"							// The manner of the new entity
		"faction"		"Items"								// The faction of the new entity
		"initState"		"st_init"							// The init state of the new entity
		"itemType"		"3"	// ITM_P3_SHIT					// The item type of the new entity (look inside Inventory func page)
	}
}
```

