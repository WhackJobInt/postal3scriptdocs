# AngleTo
<p>Get the angle difference between us and another object on the vertical axis (Yaw).
<h1>Syntax</h1>
<p><code class="language-js">AngleTo:[object]</code> -- Returns the angle difference to the specified object
<pre><code class="language-js">
// If the angle to our target is less than 30, then we'll to try and attack them!
IfAttr "AngleTo:target < 30 Pattern pt_attack"
</code></pre>