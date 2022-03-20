# Visible
<p>Check if a specified object is visible, and if the entity is currently facing it
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>This function does not rely on <code>Senses</code> function.</p> 
</div>

<h1>Syntax</h1>
<p><code class="language-js">Visible:[object]</code> -- Returns if the specified object is visible and currently facing towards it, or not
<pre><code class="language-js">
// Make sure we are able to see
Senses true

// If we can fire our weapon and we can see the targeted object...
IfAttr "Timer:tCanFire == 0 and Visible:target == 1 Block begin"
    // Try to shoot at the target, say we're shooting, and reset our fire timer
    ExecutePattern st_combat_logic.xpt_TryShoot
    ExecutePattern .xpt_SayShoot
    ExecutePattern .xpt_SetFireTimer
Block end
</code></pre>