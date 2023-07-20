# Input Functions
These are all the input functions implemented which can be invoked via <code>FireInput</code> or <code>EntFireInput</code>.

!!! warning "TODO"

    Is <code>EntFireInput</code> capable of firing non-void functions?

|			Player		  		| 	  All Entities 		| 	  All P3 NPCs 		|
|:------------------------------|:----------------------|:----------------------|
| OnSquadMemberKilled 			| Kill 					| InteractivePowerDown 	|
| DisableFlashlight 			| KillHierarchy 		| HeadTurningOff 		|
| EnableFlashlight 				| Use 					| HeadTurningOn 		|
| ForceDropPhysObjects 			| ClearParent 			| SetHabitatID 			|
| RequestPlayerHealth 			| EnableDamageForces 	| EnableCollisionCheck 	|
| SetFlashlightSlowDrain 		| DisableDamageForces 	| DisableCollisionCheck |
| SetFlashlightNormalDrain 		| DisableShadow 		| StepOffVehiclePath 	|
| RequestAmmoState 				| EnableShadow 			| SetLeanGroup 			|
| LowerWeapon 					| ---					| ---					|
| EnableCappedPhysicsDamage 	| ---					| ---					|
| DisableCappedPhysicsDamage 	| ---					| ---					|
| SuppressCrosshair 			| ---					| ---					|
| CreateDouble 					| ---					| ---					|
| DestroyDouble 				| ---					| ---					|
| EnableControl 				| ---					| ---					|
| DisableControl 				| ---					| ---					|
| ShootingEnable 				| ---					| ---					|
| ShootingDisable 				| ---					| ---					|
| ClearEventList 				| ---					| ---					|
| HolsterWeapon 				| ---					| ---					|
| UnholsterWeapon 				| ---					| ---					|
| DisableWeaponSwitching 		| ---					| ---					|
| EnableWeaponSwitching 		| ---					| ---					|

|	Hugo Chavez	| Sim Driver   | Logic/Traffic Entity |
|:--------------|:-------------|:---------------------|
| StartForward	| StartForward | Enable				  |
| Stop			| Stop		   | Disable			  |
| StopFiring	| StartFiring  | Toggle				  |
| Show			| StopFiring   | ---				  |
| Hide			| LeaveVehicle | ---				  |



|Helicopter					|
|---------------------------|
| Activate                  |
| GunOn                     |
| GunOff                    |
| MissileOn                 |
| MissileOff                |
| EnableRotorWash           |
| DisableRotorWash          |
| MoveTopSpeed              |
| EnableRotorSound          |
| DisableRotorSound         |
|                           |
| StartPatrol               |
| StopPatrol                |
| StartBreakableMovement    |
| StopBreakableMovement     |
| ChooseFarthestPathPoint   |
| ChooseNearestPathPoint    |
| InputStopLeading          |
| StartPatrolBreakable      |
|                           |
| OmniscientOn              |
| OmniscientOff             |
| BlindfireOn               |
| BlindfireOff              |
| SelfDestruct              |
| SetDockingBBox            |
| SetNormalBBox             |
| EnableGroundAttack        |
| DisableGroundAttack       |
| StartDefault              |
| StartHunt                 |
| StartCover                |

