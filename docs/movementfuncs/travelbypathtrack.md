# TravelByPathTrack
<p>Forces an NPC's movement to be limited by Path tracks
<h1>Syntax</h1>
<p><code class="language-js">TravelByPathTrack [name of path track in hammer]</code> -- Limit movement to this Pathtrack
<h1>Example</h1>
<pre><code class="language-js">
// from ai_mission_gri.p3s
st_moveout
{
	group Neutral
	patterns
	{
		pt_default
		{
			actions
			{
				// This is our target
				TargetEntByName target_rhino
				
				// Move according to "pt_rhino1" named Path track
				TravelByPathTrack pt_rhino1
				
				// Do this until we reached our target
				// Then exit from this state
				IfAttr "DistTo:target < ED_CLOSE State st_start"
				Repeat 1
			}
		}
	}
	events
	{
		OnRunOut "State st_start"
		OnUser1 "Pattern st_start.pt_goberserk"
	}
}

st_start
{
	group Neutral
	patterns
	{
		pt_default
		{
			actions
			{         
				IfAttr "Crazy == 1 State st_berserk"
				
				// Reset our movement so we are no longer bounded by Path track
				SetAreaGroup AG_DEFAULT:walkable,AG_rhino
				FreeMovementParams area_all,-1,-1,area_group
				FreeMovement run
				ExecutePattern pt_gallop
			}
		}
	}
}
</code></pre>