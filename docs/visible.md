# Visible
<p>Check if a specified entity is visible
<p>If 'Senses' is turned off, the NPC will never be able to "see" the target. 
<pre><code class="language-js">
// Make sure we are able to see
Senses true

// If we can fire our weapon and we can see the targeted entity...
IfAttr "Timer:tCanFire == 0 and Visible:target == true Block begin"
    // Try to shoot at the target, say we're shooting, and reset our fire timer
    ExecutePattern st_combat_logic.xpt_TryShoot
    ExecutePattern .xpt_SayShoot
    ExecutePattern .xpt_SetFireTimer
Block end
</code></pre>