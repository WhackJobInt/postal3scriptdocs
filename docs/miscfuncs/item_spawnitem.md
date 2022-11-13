# ItemFunctions

## Item
<p>Interact with a currently targeted or held item</p>

<h2>Syntax</h2>
<p><code class="language-js">Item [action]</code> -- Perform an action with the held item (kill, drop, throw, or use)</p>
<p><code class="language-js">Item take,[attachmentpoint]</code> -- Take the item with a specified attachment point</p>
<p><code class="language-js">Item throw,[attachmentpointdirection]</code> -- Throw the item at a specified attachmentpoint direction</p>
<p><code class="language-js">Item kill,[blendtime]</code> -- Dematerialize the item in a specified amount of time then kill/destroy it</p>

<div class="admonition warning">
<p class="admonition-title">Warning</p>
<p>- "Item" also refers to weapon or corpse/limb pickups</p>
<p>- NPCs aren't able to pick up weapons off the ground, or interact them in any way in P3S, this is a bug (this is fixed in Catharsis Reborn)</p>
</div>

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Here's a list of all the action types:
<code>take</code>, <code>kill</code>, <code>drop</code>, <code>throw</code>, <code>use</code></p>
<p>The <code>attachmentpointdirection</code> parameter takes in the name of the attachment point that is related to the orientation of the NPC,
the only attachment point bone direction that is actually used in the p3s scripts is <code>forward</code>.</p>

</div>

<h2>Example</h2>
<pre><code class="language-js">
pt_default
{
	actions
	{
		// In order to take an item you need to target the entity first!
		TargetEntByName yummy_item

		// Take the targeted item entity...
		Item take,hand_right

		// In order to interact with a held item you must target it first!
		TargetItem 1

		// Drop the held item...
		Item drop

		// Use the held item...
		Item use

		// Throw the held item forwards...
		Item throw,forward

		// Dematerialize the held item in 0.5 seconds and destroy/kill it...
		Item kill,0.5
	}
}

</code></pre>

<br>
## SpawnItem
<p>Cause an existing <code>p3_item_spawner</code> entity to spawn an item, and do stuff with the spawned item.</p>

<h2>Syntax</h2>
<p><code class="language-js">SpawnItem [spawnername],[destinationtype],[attachmentpoint],[blendtime]</code> -- Spawn the held item</p>

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Here's a list of all the destination types:
<code>owner</code>, <code>target</code>, <code>caller</code>, <code>point</code></p>
<p>The <code>point</code> destination type uses the default <code>p3_item_spawner</code> entity spawn logic</p>
<p>The <code>attachmentpoint</code> parameter is any bone name of an NPC for example</p>
<p>The <code>blendtime</code> parameter controls how fast the spawned item will take to fully "materialize"</p>
<p>The <code>attachmentpoint</code> parameter does not need to be specified or nulled out if you use the <code>point</code> destination type</p>
</div>

<h2>Example</h2>
<pre><code class="language-js">
pt_default
{
	actions
	{
		// Tell our cellphone spawner entity to spawn a cellphone item,
		// make the owner us, and put it in our right hand...
		SpawnItem "spawner_cellphone,owner,hand_right"

		// Spawn a drocha item (pornworld jizz rag) using the 
		// default p3_item_spawner spawning logic, and fully materialize it in 0.5 seconds
		SpawnItem spawn_droch,point,0.5
	}
}
</code></pre>