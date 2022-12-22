## Inventory

<p>Handles an NPC's inventory.</p>

<div class="admonition warning">
<p class="admonition-title">Catharsis Reborn Feature</p>
<p>The following function will only work in <b>Catharsis Reborn</b>.</p>
</div>

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Use <code>Object:inventory</code> to check if there's a valid selected inventory item.</p>
<p>Recommended to use <code>IfHasItem</code> if you want to do complex behavior.</p>
</div>

<h1>Syntax</h1>

<pre><code>
// From AI_CR_ItemID.p3s
Const ITM_P3_GENERIC,0 	// Equal to ITM_UNKNOWN
Const ITM_P3_PIZZA,1 	// unused
Const ITM_P3_BONE,2 	// unused
Const ITM_P3_SHIT,3
Const ITM_P3_DROCHA,4
Const ITM_P3_MONKEY,5
Const ITM_P3_CATNIP,6
Const ITM_P3_SEED,7 	// unused
Const ITM_P3_PAINTBUCKET,8
Const ITM_P3_PAINT,9
Const ITM_P3_ACID,10 	// used by zombie split
Const ITM_P3_DUMMY1,11 	// unused
Const ITM_P3_DUMMY2,12 	// unused

Const ITM_DEADPIGEON,80
Const ITM_BONE,81

Const ITM_UNKNOWN,100 	// Equal to ITM_P3_GENERIC
Const ITM_STATS,101 	// Do not use
Const ITM_CASH,102 		// Do not use

Const ITM_PIZZA,103
Const ITM_BEER,104
Const ITM_CRACKPIPE,105
Const ITM_KEVLAR,106
Const ITM_MEDKIT,107



Const ITM_COLA,111
Const ITM_WATERCUP,112

Const ITM_COPOUTFIT,114

Const ITM_DUDECLOTHES,116 // Not recommended
Const ITM_STEROIDS,117
Const ITM_ADRENALINE,118



Const ITM_DETONATOR,121 // Do not use, used by the Player's C4 weapon
</code></pre>

<p><code>Inventory select,first</code> -- Selects the first item from the NPC's inventory, if there's any.</p>
<p><code>Inventory select,last</code> -- Selects the last item from the NPC's inventory, if there's any.</p>
<p><code>Inventory select,random</code> -- Selects a random item from the NPC's inventory, if there's any.</p>
<p><code>Inventory select,[itemid]</code> -- Selects a specified item from the NPC's inventory, if there's any.</p>
<p><code>Inventory equip</code> -- Equips selected item, places it onto the NPC's hand, and removes the item from their inventory.</p>
<p><code>Inventory add,[itemid],[amount]</code> -- Adds specified item X amount into NPC's inventory.</p>
<p><code>Inventory remove,[itemid],[amount]</code> -- Removes specified item X amount from NPC's inventory.</p>

<h1>Example</h1>
<pre>
<code>
// Selects pizza item from the inventory, if there's any
xpt_selectitem
{
	actions
	{
		Inventory select,ITM_PIZZA
		IfAttr "Object:inventory != Object:null Block begin"
			Inventory equip
		Block end
	}
}
</code>
</pre>