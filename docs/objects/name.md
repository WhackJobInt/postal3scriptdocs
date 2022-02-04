# Name

The name of a specified object, set via Hammer

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>It is case-insensitive</p>
</div>

<h1>Syntax</h1>
<p><code class="language-js">Name:[object]</code> -- Returns the name of a specified object
<pre><code class="language-js">
// If the name of our targeted object is "npc_jen"
IfAttr "Name:target == String:npc_jen Block begin"
    // Set jen's health to zero
    SetAttr "target.ea_health 0"
Block end
</code></pre>