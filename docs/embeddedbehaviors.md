# Embedded Behaviors
<p>Embedded Behaviors are the default hardcoded AIs which Postal 3 sets to certain entities on map load.</p>
<p>These behaviors can be given an AI (if they are unused) providing an actual script file with the behavior name.</p>

## Default AI (Error/Missing Behavior)

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Postal 3 will fallback to this behavior if a behavior name couldn't be found, or it has too many errors in them.</p>
</div>

<div class="admonition warning">
<p class="admonition-title">Warning</p>
<p>- <code>default_behavior</code> won't override init and start states if they were pre-defined in some way.</p>
<p>- <code>Shared</code> means it'll reuse the already available parameter the entity has.</p>
</div>

<pre><code class="language-js">
Behavior Name: default_behavior
Init State: st_def_init (Shared, otherwise st_def_init)
Start State: st_default (Shared, otherwise st_default)
Manner: Shared (Some entities Manner are hardcoded, they will never be empty)
Faction: Shared (Some entities Faction are hardcoded, they will never be empty)
</code></pre>
<br>

## Anchor AI

<div class="admonition note">
<p class="admonition-title">Note</p>
<p><code>Anchor</code> function will spawn an entity with this AI. Unused.</p>
</div>

<pre><code class="language-js">
Behavior Name: Anchor
Init State: st_def_init
Start State: st_default
Manner: Anchor
Faction: Anchor
</code></pre>
<br>

## Weapon AI

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>All weapons in the game have this AI. Unused.</p>
</div>

<div class="admonition warning">
<p class="admonition-title">Warning</p>
<p>Scriptable weapons are not possible, weapons will not have any working P3S scripting attached to them.</p>
</div>

<pre><code class="language-js">
Behavior Name: itmWeapon
Init State: itm_weapon
Start State: st_default
Manner: itmWeapon
Faction: Items
</code></pre>
<br>

## Flame FX AI

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Any entity on fire will have a second entity spawned on them with this AI.</p>
</div>

<pre><code class="language-js">
Behavior Name: Flame
Init State: fx_init_flame
Start State: fx_flame
Manner: Flame
Faction: Effects
</code></pre>
<br>

## Catnip Mark AI

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Spraying catnip will spawn an entity with this AI.</p>
</div>

<pre><code class="language-js">
Behavior Name: bh_catnip_dot
Init State: catnip_init
Start State: catnip
Manner: Catnip
Faction: Effects
</code></pre>
<br>

## Catnip AI

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Catnip on the ground. Unused.</p>
</div>

<pre><code class="language-js">
Behavior Name: default_behavior
Init State: st_def_init
Start State: itm_catnip
Manner: itmCatnip
Faction: Items
</code></pre>
<br>

## Laserdot AI

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>The Laser's AI that comes out from the Player's laserpen.</p>
</div>

<pre><code class="language-js">
Behavior Name: bh_laserdot
Init State: st_init_laserdot
Start State: st_laserdot
Manner: LaserDot
Faction: LaserDot
</code></pre>
<br>

## Player AI

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>The Player's AI.</p>
</div>

<pre><code class="language-js">
Behavior Name: bh_player
Init State: st_player_init
Start State: st_player
Manner: Player
Faction: Player
</code></pre>
<br>

## Corpse AI

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>The corpse's AI. Reuses the victim's behavior, manner, and faction.</p>
</div>

<pre><code class="language-js">
Behavior Name: Shared (it is always the behavior name of the victim)
Init State: st_init_corpse
Start State: st_corpse
Manner: Shared (it is always the Manner of the victim)
Faction: Shared (it is always the Faction of the victim)
</code></pre>
<br>

## Motorhead AI

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Motorhead's AI.</p>
</div>

<pre><code class="language-js">
Behavior Name: bh_motorhead
Init State: st_init
Start State: st_start
Manner: MonkeyApe
Faction: Animals
</code></pre>
<br>

## Monkey AI

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Monkey's AI (not Motorhead). Start and init states won't be overridden if they were already defined in the map.</p>
</div>

<pre><code class="language-js">
Behavior Name: Predefined (uses predefined behavior name from the map if there is any)
Init State: p3_wild_monkey_init (if there is no predefined init state)
Start State: p3_wild_monkey (if there is no predefined start state)
Manner: MonkeyApe
Faction: Animals
</code></pre>
<br>

## Krotchy Grenade AI

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Krotchy Grenade's AI. Unused.</p>
</div>

<pre><code class="language-js">
Behavior Name: default_behavior
Init State: st_def_init
Start State: itm_toy
Manner: itmKrotchyToy
Faction: Items
</code></pre>
<br>

## Seed AI

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Leftover from unfinished Seed weapon. The projectile's AI. Unused.</p>
</div>

<pre><code class="language-js">
Behavior Name: default_behavior
Init State: st_def_init
Start State: itm_seed
Manner: itmSeed
Faction: Items
</code></pre>
<br>

## Taser FX AI

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Taser's beam AI. Unused.</p>
</div>

<pre><code class="language-js">
Behavior Name: default_behavior
Init State: st_def_init
Start State: fx_taserbeam
Manner: fxTaserBeam
Faction: Effects
</code></pre>
<br>