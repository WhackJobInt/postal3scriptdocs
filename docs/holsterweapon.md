# HolsterWeapon
<p>Deleted Postal3Script function
<p>Holsters or Unholsters NPC's stored weapon, superseded by "Weapon"
<h1>Syntax</h1>
<p><code class="language-js">HolsterWeapon [boolean]</code> -- Holsters or Unholsters NPC's stored weapon
<h1>Example</h1>
<pre><code class="language-js">
// from ai_st11_urza.p3s
pt_disarm
{
	actions
	{
		HolsterWeapon true
		Arm false
		SetAttr "ea_armed 0"
	}
}
</code></pre>