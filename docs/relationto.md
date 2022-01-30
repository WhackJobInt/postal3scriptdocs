# RelationTo
<p>Check the relation of a specified object.
<h1>Syntax</h1>
<p><code class="language-js">RelationTo:[object]</code> -- Returns the "Relation" towards this object, see "Relation" page
<h1>Example</h1>
<pre><code class="language-js">
// If the relation to our caller is of enemy, target them!
IfAttr "RelationTo:caller == Relation:enemy Block begin"
    TargetCaller 1
Block end
</code></pre>