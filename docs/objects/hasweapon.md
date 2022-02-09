# HasWeapon
<p>Checks if an NPC has a melee/ranged weapon, holstered, or equipped.</p>
<h1>Syntax</h1>
<p><code class="language-js">HasWeapon:Ranged</code> -- Ranged weapon object</p>
<p><code class="language-js">HasWeapon:Melee</code> -- Melee weapon object</p>

<h1>Example</h1>
<pre><code class="language-js">
// (from ai_badger_test.p3s)
IfAttr "HasWeapon:ranged == 2 SetAttr equipped 1" // NPC has ranged weapon equipped
IfAttr "HasWeapon:ranged == 1 SetAttr has 1" // NPC has ranged weapon holstered
IfAttr "HasWeapon:ranged == 0 SetAttr doesnt_has 1" // NPC doesn't have a ranged weapon
</code></pre>