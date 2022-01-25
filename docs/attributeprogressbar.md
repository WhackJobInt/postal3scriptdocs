# AttributeProgressBar
<p>Adds a HUD on the screen with name, and value
<p>Mainly used for displaying Health for Bosses, Allies from missions
<p>Uses .res files from "Postal III/p3/resource/UI/Hud/" folder
<h1>Syntax</h1>
<p><code class="language-js">AttributeProgressBar "[panel], show, [attribute]"</code> -- Shows or creates Progress Bar
<p><code class="language-js">AttributeProgressBar "[panel], show, [attribute], show_value"</code> -- Shows or creates Progress Bar with Attribute's value shown
<p><code class="language-js">AttributeProgressBar "[panel], hide"</code> -- Hides Progress Bar
<h1>Example</h1>
<pre><code class="language-js">
// from ai_cashmart_npc.p3s, Helicopter from Cashmart
SetAttr "flag_zombie 1"
TargetEntByName gameplay
TargetToMem msGP
SetAttr "ea_dmg_absorb 95"
TargetPlayer 1
FireInput self,StartHunt

// Show the Panel on spawn
// "./Postal III/p3/resource/UI/Hud/HeliHealthPanel.res"
AttributeProgressBar "HeliHealthPanel,show,ea_health"

Timer tShout,5:2
</code></pre>