# AddFluid

Unused Postal3Script function.

<p>Spawn gasoline fluid at a specified location.</p>

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Equivalent of the <code>p3_fluids_addgasoline</code> console command.</p>
</div>

<h1>Syntax</h1>
<p><code class="language-js">AddFluid [xpos],[ypos],[zpos],[amount]</code> -- Spawns gasoline fluid</p>

<p></p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Default amount is '300' if no amount is provided.</p>
</div>

<h1>Example</h1>
<pre><code class="language-js">
pt_default
{
	actions
	{
		// From ai_mission_pdb.p3s
		Wait 0.9
		EntFireInput tutor03_teleport,Teleport
		EntFireInput "pcc,Command:use p3_weapon_emptyhands"
		EntFireInput "lpp,RemoveWeapon:p3_weapon_grenade"
		
		// Spawn Gasoline trails at this location
		AddFluid "171,670,100,300000"
		AddFluid "-318,931,80,300000"
		AddFluid "150,925,100,100000"
		AddFluid "-110,1030,80,200000"
		
		// This would also spawn Gasoline trails at this location
		AddFluid "300,312,100"
		
		EntFireInput "pcc,Command:give p3_weapon_match"
		Wait 0.5
		MissionLog "add_primary,tutor04,#P3_PDB_T04_LOG"
		ShowMessage #P3_PDB_T04_MSG01
	}
}
</code></pre>