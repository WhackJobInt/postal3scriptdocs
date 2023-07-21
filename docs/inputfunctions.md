# Input Functions
These are all the input functions implemented which can be invoked via  
<code>FireInput</code> (only void functions) or <code>EntFireInput</code>.

| Player                                							| All Entities                                                   		|
|-------------------------------------------------------------------|-----------------------------------------------------------------------|
| IgnoreFallDamage                     *(float)*                    | SetTeam                              *(int)*                      	|
| IgnoreFallDamageWithoutReset         *(float)*                    | Kill                                 *(void)*                     	|
| OnSquadMemberKilled                  *(void)*                     | KillHierarchy                        *(void)*                     	|
| DisableFlashlight                    *(void)*                     | Use                                  *(void)*                     	|
| EnableFlashlight                     *(void)*                     | Alpha                                *(int)*                      	|
| ForceDropPhysObjects                 *(void)*                     | AlternativeSorting                   *(bool)*                     	|
| RequestPlayerHealth                  *(void)*                     | Color                                *(RGBA)*     					|
| SetFlashlightSlowDrain               *(void)*                     | SetParent                            *(string)*                   	|
| SetFlashlightNormalDrain             *(void)*                     | SetParentAttachment                  *(string)*                   	|
| SetPlayerHealth                      *(int)*                      | SetParentAttachmentMaintainOffset    *(string)*                   	|
| RequestAmmoState                     *(void)*                     | ClearParent                          *(void)*                     	|
| LowerWeapon                          *(void)*                     | SetDamageFilter                      *(string)*                   	|
| EnableCappedPhysicsDamage            *(void)*                     | EnableDamageForces                   *(void)*                     	|
| DisableCappedPhysicsDamage           *(void)*                     | DisableDamageForces                  *(void)*                     	|
| SetLocatorTargetEntity               *(string)*                   | DispatchEffect                       *(string)*                   	|
| SuppressCrosshair                    *(void)*                     | DispatchResponse                     *(string)*                   	|
| CreateDouble                         *(void)*                     | AddContext                           *(string)*                   	|
| DestroyDouble                        *(void)*                     | RemoveContext                        *(string)*                   	|
| EnableControl                        *(void)*                     | ClearContext                         *(string)*                   	|
| DisableControl                       *(void)*                     | DisableShadow                        *(void)*                     	|
| GiveItemToPlayer                     *(string)*                   | EnableShadow                         *(void)*                     	|
| GiveItemToDouble                     *(string)*                   | AddOutput                            *(string)*                   	|
| SwitchWeapon                         *(string)*                   | FireUser1                            *(string)*                   	|
| DamagePlayer                         *(int)*                      | FireUser2                            *(string)*                   	|
| GiveWeapon                           *(string)*                   | FireUser3                            *(string)*                   	|
| RemoveWeapon                         *(string)*                   | FireUser4                            *(string)*                   	|
| RemoveAllWeapon                      *(string)*                   | FireFSMScriptEvent                   *(string)*                   	|
| WeaponFire                           *(float)*                    | SetState *(string)*                                                   |
| WeaponAltFire                        *(float)*                    | SetAttribute *(string)*                                               |
| ShootingEnable                       *(void)*                     | ChangeAttribute *(string)*                                            |
| ShootingDisable                      *(void)*                     | SetFSMTarget *(string)*                                               |
| ClearEventList                       *(void)*                     | ---                                                                   |
| HolsterWeapon                        *(void)*                     | ---                                                                   |
| UnholsterWeapon                      *(void)*                     | ---                                                                   |
| DisableWeaponSwitching               *(void)*                     | ---                                                                   |
| EnableWeaponSwitching                *(void)*                     | ---                                                                   |
| Say                                  *(string)*                   | ---                                                                   |


| 	  All P3 NPCs 					| Hugo Chavez                                                    	| Sim Driver                                         |
|:----------------------------------|-------------------------------------------------------------------|----------------------------------------------------|
| InteractivePowerDown *(void*) 	| SetDriversMaxSpeed                   *(float)*                    | SetDriversMaxSpeed     *(float)*                   |
| HeadTurningOff *(void)* 			| SetDriversMinSpeed                   *(float)*                    | SetDriversMinSpeed     *(float)*                   |
| HeadTurningOn *(void)* 			| StartForward                         *(void)*                     | StartForward           *(void)*                    |
| SetHabitatID *(int)* 				| Stop                                 *(void)*                     | Stop                   *(void)*                    |
| EnableCollisionCheck *(void)* 	| StartFiring                          *(string)*                   | StartFiring            *(void)*                    |
| DisableCollisionCheck *(void)* 	| StopFiring                           *(void)*                     | StopFiring             *(void)*                    |
| StepOffVehiclePath *(void)* 		| Show                                 *(void)*                     | GotoPathCorner         *(string)*                  |
| SetLeanGroup *(string)* 			| Hide                                 *(void)*                     | EnterVehicle           *(string)*                  |
| ---								| GotoPathCorner                       *(string)*                   | LeaveVehicle           *(void)*                    |

| Logic Entity 			| Traffic Entity		|
|:----------------------|:----------------------|
| Enable *(void)*		| Enable *(void)* 		|
| Disable *(void)*		| Disable *(void)*		|
| Toggle *(void)*		| Toggle *(void)*		|
| SetUpdateTime *(float)*| SetPeriod *(float)* 	|
| ---				  	| SetCooldown *(float)*	|



| Helicopter                                                    	|
|-------------------------------------------------------------------|
| SetTrack                            *(string)*                   	|
| FlyToSpecificTrackViaPath           *(string)*                   	|
| StartPatrol                         *(void)*                     	|
| StopPatrol                          *(void)*                     	|
| StartBreakableMovement              *(void)*                     	|
| StopBreakableMovement               *(void)*                     	|
| ChooseFarthestPathPoint             *(void)*                     	|
| ChooseNearestPathPoint              *(void)*                     	|
| InputStartLeading                   *(int)*                      	|
| InputStopLeading                    *(void)*                     	|
| StartPatrolBreakable                *(void)*                     	|
| FlyToPathTrack                      *(string)*                   	|
|	                                                                |
| Activate                            *(void)*                     	|
| GunOn                               *(void)*                     	|
| GunOff                              *(void)*                     	|
| MissileOn                           *(void)*                     	|
| MissileOff                          *(void)*                     	|
| EnableRotorWash                     *(void)*                     	|
| DisableRotorWash                    *(void)*                     	|
| MoveTopSpeed                        *(void)*                     	|
| MoveSpecifiedSpeed                  *(float)*                    	|
| SetAngles                           *(string)*                   	|
| EnableRotorSound                    *(void)*                     	|
| DisableRotorSound                   *(void)*                     	|
| Kill                                *(void)*                     	|
|	                                                                |
| Enable                              *(void)*                     	|
| Disable                             *(void)*                     	|
| OmniscientOn                        *(void)*                     	|
| OmniscientOff                       *(void)*                     	|
| SetPenetrationDepth                 *(float)*                    	|
| BlindfireOn                         *(void)*                     	|
| BlindfireOff                        *(void)*                     	|
| SelfDestruct                        *(void)*                     	|
| SetDockingBBox                      *(void)*                     	|
| SetNormalBBox                       *(void)*                     	|
| EnableGroundAttack                  *(void)*                     	|
| DisableGroundAttack                 *(void)*                     	|
| DoGroundAttack                      *(string)*                   	|
| StartDefault                        *(void)*                     	|
| StartHunt                           *(void)*                     	|
| StartCover                          *(void)*                     	|


