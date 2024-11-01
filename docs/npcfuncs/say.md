# Say

Make an NPC say a specified "sentence" type voice line.

Uses the name of the sentence in the related NPC's sentence script located in 
<p><code>'.\Postal III\p3\scripts\Sentences'</code></p> 

<h2>Syntax</h2>
<p><code class="language-js">Say [sentence_name]</code>
<p><code class="language-js">Say [sentence_name,sentence_name,sentence_name]</code> -- Say a random sentence out of these (You can specify as many sentence parameters as you want)
<p><code class="language-js">Say [sentence_name,priority,wait]</code> -- Say sentence with priority, and wait until the end

<div class="admonition warning">
<p class="admonition-title">TODO</p>
<p>Need to make sure that the fourth parameter is even actually the sentence priority!
<p>Need to make sure what the wait parameter actually does specifically!
</p>
</div>

<p></p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>You can specify as many sentences parameters as you want!
<p>The voice prefix is not required, <code>GAY_ONFIRE</code> can lose the <code>GAY_</code> part and instead just be <code>ONFIRE</code> for example...</p>
</div>

<p></p>
<div class="admonition warning">
<p class="admonition-title">Warning</p>
<p>If you want the PLAYER to say something you must <code>EntFireInput logic_playerproxy</code> to do a generic say instead, like so: <code>EntFireInput proxy,Say:SENTENCENAME</code>
</div>

<h1>Example</h1>
<pre><code class="language-js">
// Say a voice line...
Say ZOMB_MOAN

// Pick and say one of these voice lines randomly...
Say ZOMB_MOAN,ZOMB_CURSE,ZOMB_HIT

// Pick and say one of these voice lines randomly, 
// and specify the optional sentence priority parameter
Say ZOMB_MOAN,ZOMB_CURSE,ZOMB_HIT,0

// Pick and say one of these voice lines randomly, 
// specify the optional sentence priority parameter,
// and wait for the end of the sentence
Say ZOMB_MOAN,ZOMB_CURSE,ZOMB_HIT,0,wait
</code></pre>