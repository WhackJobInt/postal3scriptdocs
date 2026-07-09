## Inventory

<p>Handles an NPC's inventory.</p>

<div class="admonition warning">
<p class="admonition-title">Postal III Ultrapatch+Angel v1.3.0+ Feature</p>
<p>The following function will only work in <b>Postal III Ultrapatch+Angel v1.3.0 or higher</b>.</p>
</div>

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>This feature only works with Angel's inventory item manifest.</p>
<p>Use <code>Object:inventory</code> to check if there's a valid selected inventory item.</p>
<p>Recommended to use <code>IfHasItem</code> if you want to do complex behavior.</p>
</div>

<h1>Syntax</h1>

<p><code>Inventory select,first</code> -- Selects the first item from the NPC's inventory, if there's any.</p>
<p><code>Inventory select,last</code> -- Selects the last item from the NPC's inventory, if there's any.</p>
<p><code>Inventory select,random</code> -- Selects a random item from the NPC's inventory, if there's any.</p>
<p><code>Inventory select,[namespace::name]</code> -- Selects a specified item from the NPC's inventory, if there's any.</p>
<p><code>Inventory equip</code> -- Equips selected item, places it onto the NPC's hand, and removes the item from their inventory.</p>
<p><code>Inventory add,[namespace::name],[amount]</code> -- Adds specified item X amount into NPC's inventory.</p>
<p><code>Inventory remove,[namespace::name],[amount]</code> -- Removes specified item X amount from NPC's inventory.</p>

<h1>Examples</h1>
<pre>
<code>
// Selects pizza item from the inventory, if there's any
xpt_selectitem
{
	actions
	{
		Inventory select,angel::pizza
		IfAttr "Object:inventory != Object:null Block begin"
			Inventory equip
		Block end
	}
}
</code>
</pre>
<pre>
<code>
// Adds 20 pizzas, just for fun
xpt_additems
{
	actions
	{
		Inventory add,angel::pizza,20
	}
}
</code>
</pre>