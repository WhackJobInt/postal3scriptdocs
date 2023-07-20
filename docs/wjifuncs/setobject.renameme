## SetObject

<p>Object manipulation function.</p>

<div class="admonition warning">
<p class="admonition-title">Catharsis Reborn Feature</p>
<p>The following function will only work in <b>Catharsis Reborn</b>.</p>
</div>

<div class="admonition note">
<p class="admonition-title">TODO</p>
<p>This function is a mess, should be rewritten.</p>
</div>

<h1>Syntax</h1>
<p><code>SetObject self:target,target:[target/caller/attacker/item]</code> -- Sets the entity's target to the current target's <code>[obj]</code></p>
<p><code>SetObject self:target,target:mem,[memslot]</code> -- Sets the entity's target to the current target's <code>[memslot]</code></code></p>

<h1>Example</h1>
<pre>
<code>
// This makes the entity follow an entity from the target's memory slot
xpt_followthrower
{
	actions
	{
		SetObject self:target,target:mem,DOGTOY_THROWER
		Follow true
	}
}
</code>
</pre>