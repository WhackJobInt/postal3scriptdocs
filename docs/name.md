# Name
<p>The name of any specified entity
<pre><code class="language-js">
// If the name of our targeted entity is "npc_jen"
IfAttr "Name:target == String:npc_jen Block begin"
    // Set jen's health to zero
    SetAttr "target.ea_health 0"
Block end
</code></pre>