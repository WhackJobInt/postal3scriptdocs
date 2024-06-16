# Target Functions

## TargetEnemy

Sets NPC's enemy as target object

<h2>Syntax</h2>
<p><code class="language-js">TargetEnemy 1</code> -- Sets NPC's enemy as target object</p>

<br>
## TargetPlayer

Sets Player as target object

<h2>Syntax</h2>
<p><code class="language-js">TargetPlayer 1</code> -- Sets Player as target object</p>

<br>
## TargetCaller

Sets Event's caller as target object

<h2>Syntax</h2>
<p><code class="language-js">TargetCaller 1</code> -- Sets Event's caller as target object</p>

<br>
## TargetItem

Sets item in NPC's hand as target object

!!! tip "🪽 Postal 3 Angel-only feature"
	- Works with Players
	- Can be used to get the active weapon

<h2>Syntax</h2>
<p><code class="language-js">TargetItem 1</code> -- Sets item in NPC's hand as target object</p>

<br>
## TargetVehicle

Sets named Vehicle as target object

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Caller must be a Driver NPC</p>
</div>

<h2>Syntax</h2>
<p><code class="language-js">TargetVehicle [entity name]</code> -- Sets named Vehicle as target object</p>
<p><code class="language-js">TargetVehicle null</code> -- Resets Driver's entry point</p>
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

<br>
## TargetHostage

Unused Postal3Script function.

Sets Hostage as target object.

<ul>
<div class="admonition note">
<p class="admonition-title">Note</p>
<li>Caller must be the Player</li>
<li>Player must have active Hostage</li>
</div>
</ul>

<h2>Syntax</h2>
<p><code class="language-js">TargetHostage 1</code> -- Sets Hostage as target object</p>

<br>
## TargetCrosshair

Unused Postal3Script function (Leftover from Dog School).

Sets Laserpen's dot as target object.

<div class="admonition warning">
<p class="admonition-title">Warning</p>
<p>Will fail if Player isn't using Laserpen.</p>
</div>

<h2>Syntax</h2>
<p><code class="language-js">TargetCrosshair 1</code> -- Sets Laserpen's dot as target object