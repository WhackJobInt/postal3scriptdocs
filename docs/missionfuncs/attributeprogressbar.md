# AttributeProgressBar
<p>Add a panel with a progress bar on the HUD with an associated attribute for the "progress" value.

<ul>
<div class="admonition note">
<p class="admonition-title">Note</p>
<li>Used for displaying boss/ally health bars and portraits in missions.</li>
<li>Uses .res files located in <code>'./p3/resource/UI/Hud/'</code></li>
</div>
</ul>

<h1>Syntax</h1>
<p><code class="language-js">AttributeProgressBar "[panel],show,[attribute]"</code> -- Show the progress bar panel with the attribute's value hidden
<p><code class="language-js">AttributeProgressBar "[panel],show,[attribute],show_value"</code> -- Show the progress bar panel with the attribute's value shown as well
<p><code class="language-js">AttributeProgressBar "[panel],hide"</code> -- Hide the progress bar
<h1>Example</h1>
<pre><code class="language-js">
// (From ai_cashmart_npc.p3s, Cashmart Helicopter boss)
SetAttr "flag_zombie 1"
TargetEntByName gameplay
TargetToMem msGP
SetAttr "ea_dmg_absorb 95"
TargetPlayer 1
FireInput self,StartHunt

// Show the Panel and assign our health attribute
// ("Postal III/p3/resource/UI/Hud/HeliHealthPanel.res")
AttributeProgressBar "HeliHealthPanel,show,ea_health"

Timer tShout,5:2
</code></pre>