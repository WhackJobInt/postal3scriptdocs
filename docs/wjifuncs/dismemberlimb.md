## DismemberLimb

<p>Dismembers a Human target's limb.</p>

<div class="admonition warning">
<p class="admonition-title">Catharsis Reborn Feature</p>
<p>The following function will only work in <b>Catharsis Reborn</b>.</p>
</div>

<h1>Syntax</h1>
<pre><code>
// Limbs
Const LIMB_LEFTARM,4
Const LIMB_RIGHTARM,5
Const LIMB_LEFTLEG,6
Const LIMB_RIGHTLEG,7
</code></pre>

<p><code>DismemberLimb [pointer],[min],[max]</code> -- Dismembers a Human target's limb</p>
<p><code>DismemberLimb [pointer]</code> -- Dismembers a Human target's random limb</p>

<h1>Example</h1>
<pre><code class="language-js">
// From Motorhead's CR AI
xpt_melee_attack_distcheck
{
    actions
    {
        IfAttr "DistTo:target <= 45 Block begin"
            Push self,target,hard,true,true
            DismemberLimb target,LIMB_LEFTLEG,LIMB_RIGHTLEG
        Block end
    }
}
</code></pre>