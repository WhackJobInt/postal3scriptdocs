# Ammo
<p>Unused Postal3Script Object
<p>Checks an NPC's primary ammo value.</p>

<div class="admonition warning">
<p class="admonition-title">Warning</p>
<p>Postal 3 doesn't have proper ammo handling or check for NPCs, it's a broken or underdeveloped feature. It's advised to come up with your own Ammo system in p3s.</p>
</div>

<h1>Example</h1>
<pre><code class="language-js">
// (Possible example)
xpt_CheckAmmo
{
	actions
	{
		IfAttr "ea_ammo > 0 SetAttr HaveAmmo 1"
		IfAttr "ea_ammo <= 0 SetAttr NoAmmo 1"
		
		IfAttr "Ammo:self > 0 SetAttr HaveAmmo 1"
		IfAttr "Ammo:self <= 0 SetAttr NoAmmo 1"
	}
}
</code></pre>