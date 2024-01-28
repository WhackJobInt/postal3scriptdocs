# Paradise Bridge (ai_mission_pdb.p3s)
<h1>Pre-Path</h1>

This is where most of the Players felt really disappointed with the game. Oh also, grenades are very happy to crash the game!

<p>Below you will only see the behavior names, and a rough guessing from the code on what they were supposed to do.
<p>Unused behavior name(s) from script file:
<pre><code class="language-js">
'bh_look_tut_point' - Checks for Player Line of Sight, executes events according if Player is looking at it
</code></pre>
<p>All used behavior names in the level:
<pre><code class="language-js">
'bh_zombie_eater'
'bh_zombie02_eater'
'bh_zombie01'
'bh_zombie02'
'bh_zombie03'
'bh_swat01'
'bh_swat03' -- This is not an error, bh_swat02 does not exists
'bh_pdb_champ'
'bh_mission_pdb'
</code></pre>
<p>State 'st_tutor04' from 'bh_mission_pdb' is unused
<p>It involved the game spawning gasoline trails, then giving the player a match to lit them up, before eventually going to the Zombies to roast them.
<pre><code class="language-js">
st_tutor04 //не используется, оставил на всякий случай
{
	Group Neutral
	Patterns
	{
		pt_default
		{
			actions
			{
				//PlayVideo pdb_04,1.0,1.0
				Wait 0.9
				EntFireInput tutor03_teleport,Teleport
				EntFireInput "pcc,Command:use p3_weapon_emptyhands"
				EntFireInput "lpp,RemoveWeapon:p3_weapon_grenade"
				//EntFireInput tutor04_clip,Enable
				//EntFireInput tutor04_escape_tg,Enable
				//MissionLog remove,tutor03_01
				//MissionLog remove,tutor03_02
				AddFluid "171,670,100,300000"
				AddFluid "-318,931,80,300000"
				AddFluid "150,925,100,100000"
				AddFluid "-110,1030,80,200000"
				EntFireInput "pcc,Command:give p3_weapon_match"
				//EntFireInput "pcc,Command:use p3_weapon_match"
				Wait 0.5
				MissionLog "add_primary,tutor04,#P3_PDB_T04_LOG"
				ShowMessage #P3_PDB_T04_MSG01
			}
			events
			{
				OnTutor04ZombiesDead	"Pattern pt_end"
			}
		}
		
		pt_end
		{
			actions
			{
				MissionLog done,tutor04
				State st_tutor05
				//EntFireInput tutor04_block,disable
				//EntFireInput tutor04_block_tg,disable
			}
			events
			{
				OnTutorial05Start "State st_tutor05"
			}
		}
	}
}
</code></pre>