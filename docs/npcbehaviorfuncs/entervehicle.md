# EnterVehicle
<p>Forces NPC to enter into a vehicle if it's near to it</p>

<ul>
<div class="admonition note">
<p class="admonition-title">Note</p>
<li>NPC must be a Driver</li>
<li>Must be used in combination with <a href="../../targetingfuncs/targetfunctions/#targetvehicle">TargetVehicle</a></li>
</div>
</ul>

<h2>Syntax</h2>
<p><code class="language-js">EnterVehicle 1</code> -- NPC enters into vehicle
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
				// Target reached, so try entering into vehicle
                OnTargetReach "EnterVehicle 1"
                OnEnteredVehicle "Pattern pt_vehicle"
            }
        }
    }
}
</code></pre>