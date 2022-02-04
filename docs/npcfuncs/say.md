# Say

Make an NPC say a specified "sentence" type voice line.

Uses the name of the sentence in the related NPC's sentence script located in 
<p><code>'.\Postal III\p3\scripts\Sentences'</code></p> 

<p></p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>The voice prefix is not required, <code>GAY_ONFIRE</code> can lose the <code>GAY_</code> part and instead just be <code>ONFIRE</code> for example...</p>
</div>

<p></p>
<div class="admonition tip">
<p class="admonition-title">Tip</p>
<p>If you want the player to say something you must <code>EntFireInput logic_playerproxy</code> to do a generic say instead, like so: <code>EntFireInput proxy,Say:SENTENCENAME</code>
</div>

<pre><code class="language-js">
// Say a voice line...
Say ZOMB_MOAN

// Pick and say one of these voice lines randomly...
Say ZOMB_MOAN,ZOMB_CURSE,ZOMB_HIT

// Pick and say one of these voice lines randomly, and specify the optional sentence
// priority parameter (TODO: Need to make sure that is actually what that parameter even is)
// SENTENCE PRIORITY PARAMETERS
// SENTENCE_PRIORITY_NORMAL = 0,
// SENTENCE_PRIORITY_MEDIUM = 1,
// SENTENCE_PRIORITY_HIGH = 2,
Say ZOMB_MOAN,ZOMB_CURSE,ZOMB_HIT,0
</code></pre>