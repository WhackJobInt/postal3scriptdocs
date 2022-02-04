# SetActPack

Sets NPC's animation style for activity

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Uses information from <code>'p3/scripts/ai_activities.p3s'</code> for [animation]</p>
</div>


<h1>Syntax</h1>
<p><code class="language-js">SetActPack ACT_[IDLE/WALK/RUN],[animation],[Alert/Wound]</code> -- Sets animation for activity, [Alert/Wound] is optional
<h1>Example</h1>
<pre><code class="language-js">
// If Health is lower than 55, play "run_wounded" anim when running
IfAttr "ea_health < 55 SetActPack ACT_RUN,run_wounded"

// Resets animation for ACT_IDLE
SetActPack ACT_IDLE,ACT_IDLE

// Only plays "run_panic" anim when on Alert
SetActPack ACT_RUN,run_panic,Alert

// Forcefully sets "walk_zombie" anim when wounded
SetActPack ACT_WALK,walk_zombie,Wound
</code></pre>