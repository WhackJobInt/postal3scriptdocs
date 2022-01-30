#- MissionLog
<p>Adds missions/jobs/objectives on the Player's mission log.
<h1>Syntax</h1>
<p><code class="language-js">MissionLog clear_all</code> -- Clears all objectives from the log
<p><code class="language-js">MissionLog add_primary, [obj], [text/string]</code> -- Adds primary objective to the log
<p><code class="language-js">MissionLog add_secondary, [obj], [text/string]</code> -- Adds secondary objective to the log
<p><code class="language-js">MissionLog done, [obj1], [obj2], ..</code> -- Objective(s) marked as done
<p><code class="language-js">MissionLog fail, [obj1], [obj2], ..</code> -- Objective(s) marked as failed
<p><code class="language-js">MissionLog removed, [obj1], [obj2], ..</code> -- Objective(s) removed without a trace
<p><code class="language-js">MissionLog disable</code> -- Mission log is disabled
<p><code class="language-js">MissionLog enable</code> -- Mission log is enabled
<h1>Example</h1>
<pre><code class="language-js">
// From ai_mission_jwb.p3s
st_start
{
	group Neutral
	patterns 
	{
		pt_default
		{
			actions
			{
				PlayerKarma hide
				
				EntFireInput "lpp,GiveWeapon:p3_weapon_taser"
				EntFireInput "pcc,Command:use p3_weapon_taser"
				
				ExecutePattern .xpt_show_momleft
				ExecutePattern st_util.xpt_ShowMissionDesc
				
				// Adds the objective to the Player's log "Jen must survive"
				MissionLog add_primary,JenSurvive,#P3_JWB_PRIMARY_JEN
				
				ExecutePattern .xpt_secondary
				ShowMessage #P3_JWB_START
				ShowMessage #P3_JWB_HELPER01
				
				Pattern pt_loop
			}
		}
		
		// All Soccer Moms have left
		pt_end
		{
			actions
			{
				// Objectives marked as done
				MissionLog done,MomsLeft
				MissionLog done,JenSurvive
				
				SetAttr "NonLethalDone 1"
				IfAttr "PoliceIsHere == 1 RemoveAttr NonLethalDone"
				
				// Player didn't harm anyone
				CheckAttr "NonLethalDone MissionLog done,NonLethal"
				
				EntFireInput fade_in,fade
				Wait 1
				EntFireInput "pcc,Command:video_exitcmd jwb_3 p3_end_mission"
			}
		}
	}
}
</code></pre>

<br><h1>- MissionSave</h1>
<p>Unused Postal3Script function.
<p>Not recommended to use.
<h1>Syntax</h1>
<p><code class="language-js">MissionSave [string]</code> -- Saves the game
<h2>Technical Details</h2>
<p>When "MissionSave" is called in p3s, it will do "save P3M_[string] mission [string]" in console, where [string] is replaced with the parameter.
<p>It was to be used or related to 'MissionLog', but it looks like it's underdeveloped.
<h1>Example</h1>
<pre><code class="language-js">
// This will create a p3m_b4_zombie_ambush.sav and .tga file in the SAVE folder
MissionSave b4_zombie_ambush
</code></pre>

<br><h1>- MissionBriefing</h1>
<p>Unused Postal3Script function
<p>Shows a message on the screen with black background, with a "Press ENTER to continue" prompt.
<p>Equivalent to "gameui_show_p3_briefdlg [string]" console command, which was also used ONLY in the Paradise Bridge level.
<h1>Example</h1>
<pre><code class="language-js">
// This will show the very first text screen of Paradise Bridge level
MissionBriefing "#P3_PDB_T01_ONSCREEN"

// This will do the same, but after the pdb_00.bik stopped playing after execution
EntFireInput "pcc,Command:video_exitcmd pdb_00 gameui_show_p3_briefdlg #P3_PDB_T01_ONSCREEN"
</code></pre>