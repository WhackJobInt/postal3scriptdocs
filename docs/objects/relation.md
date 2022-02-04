# Relation
<p>The relation of an NPC.
<h1>Syntax</h1>
<p><code class="language-js">Relation:[relation type]</code> -- Returns the relation type specified
<div class="admonition note">
<p class="admonition-title">All Relation Types</p>
<p><code>Relation:neutral</code> ; <code>Relation:enemy</code> ; <code>Relation:fear</code></p>
</div>
<h1>Example</h1>
<pre><code class="language-js">
// If the relation to our caller is of enemy, target them!
IfAttr "RelationTo:caller == Relation:enemy Block begin"
    TargetCaller 1
Block end
</code></pre>