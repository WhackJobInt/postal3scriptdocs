# Say
<p>Make an NPC say a specified "sentence" type voice line
<p>Uses the name of the sentence in the related NPC's sentence script located in "Postal III\p3\scripts\Sentences". The voice prefix is not required to be used. GAY_ONFIRE can lose the "GAY_" part, and instead just be ONFIRE for example.
<p>
If you want the player to say something you must EntFireInput logic_playerproxy to do a generic say instead, like this: "EntFireInput proxy,Say:SENTENCENAME".
<pre><code class="language-js">
// Say a single sentence voiceline...
Say ZOMB_MOAN,ZOMB_CURSE,ZOMB_HIT

// Say a random voice line out of these...
Say ZOMB_MOAN,ZOMB_CURSE,ZOMB_HIT

// Say a random voice line out of these, and specify an optional sentence
// priority parameter (NOTE: Might need to factcheck this) - Tim 
// SENTENCE PRIORITY PARAMETERS
// SENTENCE_PRIORITY_NORMAL = 0,
// SENTENCE_PRIORITY_MEDIUM = 1,
// SENTENCE_PRIORITY_HIGH = 2,
Say ZOMB_MOAN,ZOMB_CURSE,ZOMB_HIT,0
</code></pre>