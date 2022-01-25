# ShowMessage
<p>Prints out message to the screen
<p>Supports strings from "Postal III/p3/resource/p3_english.txt" (or from any other file that contains valid strings)
<p>Equivalent to Half-Life 2's UserMessageBegin
<p>Uses data from "Postal III/p3/scripts/HudLayout.res" (Plus "channels_manifest.txt" and "HudAnimations.txt")
<h1>Example</h1>
<pre><code class="language-js">
// This will print on the screen
ShowMessage "#P3_CM_INSANE1"

// This will print on the P3Karma channel
ShowMessage "[Ja-ja, natürlich!], $P3Karma"

// This will print on the P3Mission channel
ShowMessage "[Puff! Puff! Puff!], $P3Mission"

// This will print on the P3Debug channel
ShowMessage "[Meow!... I'm on Fear!!!], $P3Debug"

// You have arrested 0-3 of 3 hobos
ChangeAttr "HoboArrested 1"
ShowMessage "[You have arrested {0:v} of 3 hobos], $P3Mission, HoboArrested"

// Slightly more complex syntax
IfAttr "caller.ea_Manner == Manner:PussyCat and mis_004 >= 0 Block begin,execute"
	TargetEntByName mg_004
	SetAttr "mis_004 cat_counter"
	IfAttr "mis_004 >= target.condition SetAttr mis_004 target.condition"
	ShowMessage "[ {0:v} of {1:v} deceased cats have been obtained], $P3Mission, mis_004, target.condition"
Block end
</code></pre>
<br><h1>ShowHint</h1>
<p>Unused Postal3Script function
<p>Karma hinting is done automatically, so this has been left completely unused
<p>Uses data from "Postal III/p3/scripts/hints_manifest.txt"
<h1>Example</h1>
<pre><code class="language-js">
// First found in 'ai_st1_common.p3s' Line 954
ShowHint hintCat
// First found in 'ai_st6_missions.p3s' Line 528
ShowHint hintKarmaDown
ShowHint hintKarmaUp
</code></pre>