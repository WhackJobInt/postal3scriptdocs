# Say

Make an NPC say a specified "sentence" type voice line.

Uses the name of the sentence in the related NPC's sentence script located in 
<p><code>'.\Postal III\p3\scripts\Sentences'</code></p> 

<div class="admonition warning">
<p class="admonition-title">TODO</p>
<p>Need to make sure that the fourth parameter is actually even the sentence priority!</p>
</div>

<p></p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Here's a list of all the sentence priority parameters: <code>0, 1, 2</code>
(0 = normal, 1 = medium, 2 = high)
</p>

<p>The voice prefix is not required, <code>GAY_ONFIRE</code> can lose the <code>GAY_</code> part and instead just be <code>ONFIRE</code> for example...</p>
</div>

<p></p>
<div class="admonition warning">
<p class="admonition-title">Warning</p>
<p>If you want the player to say something you must <code>EntFireInput logic_playerproxy</code> to do a generic say instead, like so: <code>EntFireInput proxy,Say:SENTENCENAME</code>
</div>





<pre><code class="language-js">
// Say a voice line...
Say ZOMB_MOAN

// Pick and say one of these voice lines randomly...
Say ZOMB_MOAN,ZOMB_CURSE,ZOMB_HIT

// Pick and say one of these voice lines randomly, 
// and specify the optional sentence priority parameter
Say ZOMB_MOAN,ZOMB_CURSE,ZOMB_HIT,0
</code></pre>