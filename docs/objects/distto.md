# DistTo
<p>Check the distance between one object to another.
<h1>Syntax</h1>
<p><code class="language-js">DistTo:[object]</code> -- Returns the distance to the specified object
<pre><code class="language-js">
// "GLOBAL" ENEMY DISTANCE CONSTANTS
// Const ED_VERY_CLOSE,32
// Const ED_CLOSE,160
// Const ED_MIDDLE,320
// Const ED_FAR,768
// Const ED_FURTHER,1280
// Const ED_VERY_FAR,2048

// Turn to face the target if we're SUPER close to them
// You may use any integer or one of the above specified constants instead...
IfAttr "DistTo:target < 16 Pattern pt_face"

// Caller is pretty far, so bombard them
IfAttr "DistTo:caller > ED_FAR Pattern pt_bombard"
</code></pre>