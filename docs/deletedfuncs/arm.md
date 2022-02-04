# Arm
<p>Deleted Postal3Script function
<p>Sets melee status for the NPC, superseded by "Weapon"
<h1>Syntax</h1>
<p><code class="language-js">Arm [boolean],melee</code> -- Sets melee status, and holsters weapon if possible
<h1>Example</h1>
<pre><code class="language-js">
// from ai_st11_urza.p3s
pt_arm_melee
{
	actions 
	{
		Block Begin,Execute
			Aim false
			Arm True,melee
			IfAttr "ea_status < 1 SetAttr ea_status 1"
		Block End
	}
}
</code></pre>