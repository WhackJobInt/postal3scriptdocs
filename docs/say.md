# Say
<p>Make an NPC say a specified "sentence" type voice line.
<p>Uses the name of the sentence in the related NPC's sentence script located in "Postal III\p3\scripts\Sentences". The voice prefix is not required, "GAY_ONFIRE" can lose the "GAY_" part and instead just be "ONFIRE" for example...
<p>If you want the player to say something you must EntFireInput logic_playerproxy to do a generic say instead, like so: "EntFireInput proxy,Say:SENTENCENAME".
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