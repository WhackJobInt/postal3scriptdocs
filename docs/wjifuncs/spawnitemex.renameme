## SpawnItemEx

<p>Alternative/Extended version of SpawnItem which works with Player.</p>

<div class="admonition warning">
<p class="admonition-title">Catharsis Reborn Feature</p>
<p>The following function will only work in <b>Catharsis Reborn</b>.</p>
</div>

<h1>Syntax</h1>
`SpawnItemEx "<name from cr_spawnitem.txt>,Object:<obj>,<takeitemparam>,<blendintime>,unfixed"` -- Spawns an item on `<takeitemparam>` position, with blending.</p>
`SpawnItemEx "<name from cr_spawnitem.txt>,Object:<obj>,<takeitemparam>,<blendintime>,unfixed"` -- Spawns an item on `<takeitemparam>` position, with blending, and item stays there. (as if the entity is holding the item)</p>

<h1>Example</h1>
```
// Example code from Dog AI
st_poo
{
	Group Neutral
	Patterns
	{
		pt_default
		{
			actions
			{
				EmitSound champ_breathing
				Sequence seq.idle_poo
				WaitForEnd 1
				ResetSequence 1
				SetAttr "IsHungry 1"
				
				state st_start
			}
			events
			{
				OnAnimPOO 	"SpawnItemEx Poop,Object:self,bot,1.0,unfixed"
			}
		}
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