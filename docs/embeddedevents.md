# Embedded Events
<p>These are all Events that are highly embedded into the engine.</p>

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>If you see a typo, <b>it's not a typo</b>, it's how they were programmed into the game.</p>
</div>

## 🆙🪽 Ultrapatch Embedded Events
!!! warning "🆙🪽 Postal III Ultrapatch-only feature"
	These embedded events below will only work with Postal III Ultrapatch.
```
OnHit 					-- Helicopter
OnDeath 				-- Helicopter

OnTargetKilled 			-- Fixed buggy event

OnApplyCatnip 			-- Applied for all NPCs when using catnip weapon
OnBlinded 				-- Applied for all NPCs when using Laserpen

OnPlayerCrosshairFocus 	-- (inside entity) Called when Player is focusing on this entity
OnPlayerCrosshairLeft 	-- (inside entity) Called when Player is no longer focusing the entity
```	

## 🪽 Angel Embedded Events
!!! warning "🪽 Postal III Ultrapatch Angel-only feature"
	These embedded events below will only work with Postal III Ultrapatch Angel.
```
OnUseCommand 		-- Interactable prop
OnHurt 				-- Interactable prop
OnTouch 			-- Interactable prop, touch must be setup
OnStartTriggerTouch -- Interactable prop, touch must be setup
OnEndTriggerTouch 	-- Interactable prop, touch must be setup

OnASRestore 		-- Fired on save game load for restorable entities
OnASTransition 		-- Fired on transition for restorable entities
```

## Act Busy (unused)
<pre><code class="language-js">
OnStartBusyNode -- completely unused
OnFinishBusyNode -- completely unused
OnNoActiveNode -- completely unused
</code></pre>

## Fear (unused)
<pre><code class="language-js">
FearHide -- completely unused
</code></pre>

## Move Planning
<pre><code class="language-js">
OnInvalidRoute
OnPathTrackUnresolved -- unused, is in test script files
OnPathTrackFailed -- unused, is in test script files
OnTargetReach
OnTargetClose
OnLeanFailed
</code></pre>

## Sight
<pre><code class="language-js">
OnSeeFlame
OnSawEnemyEnt
OnSawFearEnt -- completely unused
OnSawNeutralEnt -- completely unused
OnLostEnemyEnt
OnLostFearEnt -- completely unused
OnLostNeutralEnt -- completely unused
OnVisible
OnLOS
OnLost
</code></pre>

## Hearing
<pre><code class="language-js">
OnHear
OnHearCombat
OnHearDanger
</code></pre>

## Targeting
<pre><code class="language-js">
OnTargetReset
OnEnemiesDead
OnNewEnemy -- Note: This does not execute instantly
OnNewFear -- Note: This does not execute instantly
OnTargetKilled -- completely unused, Note: buggy, acts like 'OnDeath'
OnTargetArrested
OnEnemySpoted -- unused, is in test script files
OnTargetResistArrest -- unused, is in test script files (ArrestTarget, beta cop leftover)
OnTargetUnconscious
</code></pre>

## Damage
<pre><code class="language-js">
OnIgnite
OnAcid -- Zombie projectile
OnKrotchyDamage -- unused (commented out in ai_mission_bdk.p3s), Player only with Krotchy costume
OnDamaged
OnHit
OnDeath
OnBeeSting
</code></pre>

## Stimuli
<pre><code class="language-js">
OnSuperNasty -- Urinated/Got poop
OnNasty -- Urinated/Got poop (no difference from SuperNasty)
OnPaint
OnTasingStart
OnBatonShocked
OnUnstunned
OnBump
OnTased
OnKicked
OnSprayStunned
OnStunnedOut -- completely unused
OnBlind -- completely unused (used by Laserpen, spray weapons)
OnInFlame
OnExtinguish
OnPlayerPush -- unused (commented out in ai_npc_social.p3s)
OnStandUpBegin
OnStandUpEnd
OnUnconscious
OnFallToGround
OnRecover
OnThreatOfVehicleHit -- completely unused
OnStun
OnHostaged
OnResque -- Player releases hostage
OnArrested
OnTasingFinish
</code></pre>

## Items (prop_p3_fsmitem)
<pre><code class="language-js">
OnUse -- unused, is in test script files
OnDrop -- unused, is in test script files
OnTake -- unused, is in test script files
OnIgnite
OnAcid
</code></pre>

## Items (prop_p3_fsmitem) & Cat
<pre><code class="language-js">
OnUseCommand -- Will only execute inside the item if item type is not pizza
</code></pre>

## Cat
<pre><code class="language-js">
OnLand
OnDervishBegin
OnDervishEnd
OnGrenadeAttached -- completely unused
</code></pre>

## Animals
<pre><code class="language-js">
OnSnatch
OnUnsnatch
</code></pre>

## Driver
<pre><code class="language-js">
OnFailedToEnterVehicle
OnEnteredVehicle
OnLeaveVehicle
</code></pre>

## Tank
<pre><code class="language-js">
OnCannonShoot
OnCannonDestroyed
OnGatlingShoot -- unused, commented out in ai_tank.p3s
OnGatlingDestroyed
OnLauncherShoot
OnLauncherLeftDestroyed
OnLauncherRightDestroyed
</code></pre>

## Weapons
<pre><code class="language-js">
OnThrowGrenadeFailed -- Human NPCs ONLY
OnPrimaryAttack -- Player only
OnSecondaryAttack -- Player only
OnSucked -- Player only
</code></pre>

## Other
<pre><code class="language-js">
OnEnd -- unused, is in test script files (calls when Pattern reached end)
OnUser1 -- Hammer
OnUser2 -- Hammer
OnUser3 -- Hammer
OnUser4 -- Hammer
OnDialogNo -- completely unused
OnDialogYes -- completely unused
OnFinaleWin -- Executed inside Player's behavior
</code></pre>