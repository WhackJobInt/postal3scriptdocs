# AddFluid
<p>Spawns gasoline trails at a specified location
<p>Only ever used in Paradise Bridge level.
<h1>Syntax</h1>
<p><code class="language-js">AddFluid [xpos], [ypos], [zpos], [amount]</code> -- Spawns trails
<p>Default Amount is 300 if no Amount was defined
<h1>Example</h1>
<pre><code class="language-js">
// from ai_mission_pdb.p3s
pt_default
{
	actions
	{
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
	events
	{
		OnTutor04ZombiesDead	"Pattern pt_end"
	}
}
</code></pre>