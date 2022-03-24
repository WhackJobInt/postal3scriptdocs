# Events

## What are Postal3Script events?

<p>Events are essentially "events", triggered by some source while the entity is in a state or pattern which makes you have some kind of "async" checking.</p>
<p>Some examples being of an event is, the entity is in a state called sitting, and suddenly they've got hurt, the "OnHit" event is being called because of that, which makes the Entity's state, pattern change, or even execute a pattern externally depending on what will the "OnHit" event do as it's defined in it's Postal3Script file.</p>

<div class="admonition note">
<p class="admonition-title">Types of Events</p>
<p>Events can be Global, State, or Pattern only.</p>
</div>

<h1>Global Events Example</h1>
<div class="admonition warning">
<p class="admonition-title">Warning</p>
<p>Must be placed <b>before</b> or <b>after</b> the States bracket!</p>
</div>

<pre><code class="language-js">
behavior
{
	name bh_Postal3ScriptDocs
	inherited bh_npc
	
	// Placing the events bracket here will make them global!
	events
	{
		OnHit 			"ExecutePattern st_util.xpt_ThatHurtYouKnow"
		OnISmellFood 	"State st_food"
	}
	States
	{
		st_init
		{
			Group Neutral
			Patterns
			{
				pt_default
				{
					actions
					{
						ExecutePattern bh_base:st_init.pt_default
					}
				}
			}
		}
	}
	// It works here too!
	events
	{
		OnTimer_tPoop "State st_poop"
	}
}
</code></pre>

<h1>State Events Example</h1>
<div class="admonition warning">
<p class="admonition-title">Warning</p>
<p>Must be placed <b>after</b> the State's 'Patterns' bracket!</p>
</div>
<pre><code class="language-js">
behavior
{
	name bh_Postal3ScriptDocs
	inherited bh_npc
	
	States
	{
		st_idle
		{
			Group Neutral
			Patterns
			{
				pt_default
				{
					actions
					{
						Timer tResting,60
						Pattern pt_rest
					}
				}
				
				pt_rest
				{
					actions
					{
						// Note: this animation doesn't exists in Postal 3
						Sequence seq.IDLE_SLEEP,999
					}
				}
				
				pt_wakeup
				{
					actions
					{
						// Note: this animation doesn't exists in Postal 3
						Sequence seq.IDLE_WAKEUP
						WaitForEnd 1
						Wait 2
						State st_start
					}
				}
			}
			// Events will execute in any of the patterns above!
			events
			{
				// After 60 seconds this executes
				OnTimer_tResting	"Pattern pt_wakeup"
				// I was hit by someone...
				OnHit				"Pattern pt_wakeup"
				// I'm now pissed, literally
				OnNasty				"Pattern pt_wakeup"
			}
		}
	}
}
</code></pre>

<h1>Pattern Events Example</h1>
<div class="admonition warning">
<p class="admonition-title">Warning</p>
<p>Must be placed <b>after</b> the Pattern's 'actions' bracket!</p>
</div>
<pre><code class="language-js">
behavior
{
	name bh_Postal3ScriptDocs
	inherited bh_npc
	
	States
	{
		st_idle
		{
			Group Neutral
			Patterns
			{
				pt_default
				{
					actions
					{
						Timer tResting,60
						Pattern pt_rest
					}
				}
				
				pt_rest
				{
					actions
					{
						// Note: this animation doesn't exists in Postal 3
						Sequence seq.IDLE_SLEEP,999
					}
					// These events will now only execute in pt_rest
					events
					{
						// After 60 seconds this executes
						OnTimer_tResting	"Pattern pt_wakeup"
						// I'm now pissed, literally
						OnNasty				"Pattern pt_wakeup"
						// I was hit by someone...
						OnHit				"Pattern pt_wakeup"
					}
				}
				
				pt_wakeup
				{
					actions
					{
						// Note: this animation doesn't exists in Postal 3
						Sequence seq.IDLE_WAKEUP
						WaitForEnd 1
						Wait 2
						State st_start
					}
				}
			}
		}
	}
}
</code></pre>

<br>
## Automatically Created Events
<p>There are several Postal3Script functions that automatically create Events, here you can find all of them below, and the correspending functions:</p>
<p><code class="language-js">OnAE_[name]</code> 	-- AreaEvent</p>
<p><code class="language-js">OnTimer_[name]</code> 	-- Timer</p>
<p><code class="language-js">OnAnim[animevent]</code> -- Sequence (Note: Model animations need to have an anim event embedded)</p>
<p><code class="language-js">OnAttrMin_[attribute]</code> -- ChangeAttr</p>
<p><code class="language-js">OnAttrMax_[attribute]</code> -- ChangeAttr</p>
<p><code class="language-js">OnAttrChange_[attribute]</code> -- ChangeAttr</p>
<p><code class="language-js">OnAttrRemove_[attribute]</code> -- RemoveAttr</p>
<p><code class="language-js">OnFire_[name]</code> -- Fire Functions</p>

<br>
## Embedded Events
<p>These are all Events that are highly embedded into the engine (Todo: categorize them)</p>
<pre><code class="language-js">
OnStartBusyNode
OnFinishBusyNode
OnNoActiveNode
FearHide
OnInvalidRoute
OnTargetReset
OnEnd
OnUser1
OnUser2
OnUser3
OnUser4
OnPathTrackUnresolved
OnPathTrackFailed
OnUse
OnDrop
OnTake
OnDialogNo
OnDialogYes
OnIgnite
OnAcid
OnFinaleWin
OnLeanFailed
OnKrotchyDamage
OnDamaged
OnHit
OnExtinguish
OnSuperNasty
OnNasty
OnPaint
OnInFlame
OnSeeFlame
OnPlayerPush
OnEnemiesDead
OnNewEnemy
OnNewFear
OnSawEnemyEnt
OnSawFearEnt
OnSawNeutralEnt
OnLostEnemyEnt
OnLostFearEnt
OnLostNeutralEnt
OnTased
OnTargetReach
OnStandUpBegin
OnStandUpEnd
OnLost
OnTargetClose
OnVisible
OnLOS
OnHear
OnHearCombat
OnHearDanger
OnDeath
OnTargetKilled
OnUnconscious
OnTargetUnconscious
OnKicked
OnFallToGround
OnRecover
OnThreatOfVehicleHit
OnSprayStunned
OnTasingStart
OnBatonShocked
OnUnstunned
OnBump
OnUseCommand
OnLand
OnDervishBegin
OnDervishEnd
OnGrenadeAttached
OnSnatch
OnUnsnatch
OnStun
OnHostaged
OnResque
OnArrested
OnTargetArrested
OnThrowGrenadeFailed
OnStunnedOut
OnEnemySpoted
OnTargetResistArrest
OnFailedToEnterVehicle
OnEnteredVehicle
OnLeaveVehicle
OnCannonShoot
OnCannonDestroyed
OnGatlingShoot
OnGatlingDestroyed
OnLauncherShoot
OnLauncherLeftDestroyed
OnLauncherRightDestroyed
OnPrimaryAttack
OnSecondaryAttack
OnBeeSting
OnBlind
OnSucked
OnTasingFinish
</code></pre>