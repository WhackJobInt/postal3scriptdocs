# Name
<p>The name of a specified entity, set via Hammer
<p>It is case-insensitive
<pre><code class="language-js">
// If the name of our targeted entity is "npc_jen"
IfAttr "Name:target == String:npc_jen Block begin"
    // Set jen's health to zero
    SetAttr "target.ea_health 0"
Block end
</code></pre>