#- TargetEnemy
<p>Sets NPC's enemy as target object
<h2>Syntax</h2>
<p><code class="language-js">TargetEnemy 1</code> -- Sets NPC's enemy as target object

<br><br><h1>- TargetPlayer</h1>
<p>Sets Player as target object
<h2>Syntax</h2>
<p><code class="language-js">TargetPlayer 1</code> -- Sets Player as target object

<br><br><h1>- TargetCaller</h1>
<p>Sets Event's caller as target object
<h2>Syntax</h2>
<p><code class="language-js">TargetCaller 1</code> -- Sets Event's caller as target object

<br><br><h1>- TargetItem</h1>
<p>Sets item in NPC's hand as target object
<h2>Syntax</h2>
<p><code class="language-js">TargetItem 1</code> -- Sets item in NPC's hand as target object

<br><br><h1>- TargetVehicle</h1>
<p>Sets named Vehicle as target object
<p>Caller must be a Driver NPC
<h2>Syntax</h2>
<p><code class="language-js">TargetVehicle [entity name]</code> -- Sets named Vehicle as target object
<p><code class="language-js">TargetVehicle null</code> -- Resets Driver's entry point
<h1>Example</h1>
<pre><code class="language-js">
// (from ai_mission_mc.p3s)
st_return_to_vehicle
{
	group Neutral
	patterns
	{
		pt_default:ignore_ext_events
		{
			actions
			{
				SetAttr "OnSegway 0"
				TargetVehicle vehicle_driver_exit
				MoveToTarget true,0.5
				Repeat 3
			}
			events
			{
				OnTargetReach "EnterVehicle 1"
				OnEnteredVehicle "Pattern pt_vehicle"
			}
		}
	}
}
</code></pre>

<br><br><h1>- TargetHostage</h1>
<p>Unused Postal3Script function
<p>Sets Hostage as target object
<p>Caller must be the Player, Player must have active Hostage
<h2>Syntax</h2>
<p><code class="language-js">TargetHostage 1</code> -- Sets Hostage as target object

<br><br><h1>- TargetCrosshair</h1>
<p>Unused Postal3Script function (Leftover from Dog School)
<p>Sets Laserpen's dot as target object
<p>Will fail if Player isn't using Laserpen
<h2>Syntax</h2>
<p><code class="language-js">TargetCrosshair 1</code> -- Sets Laserpen's dot as target object