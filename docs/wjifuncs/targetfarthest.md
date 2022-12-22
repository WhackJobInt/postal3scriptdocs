## TargetFarthest

<p>Targets an entity farthest (not totally farthest, around 900 radius) to the entity with filters.</p>
<p>Works with Players too.</p>

<div class="admonition warning">
<p class="admonition-title">Catharsis Reborn Feature</p>
<p>The following function will only work in <b>Catharsis Reborn</b>.</p>
</div>

<h1>Syntax</h1>
<p><code>TargetFarthest 1,[filter1],[filter2],[filter3],...</code> -- Targets farthest entity, ignored entities will never be a target.</p>
<p><code>TargetFarthest 0,[filter1],[filter2],[filter3],...</code> -- Targets farthest entity, ignored entities can be a target.</p>
<p><code>TargetFarthest [object],[filter1],[filter2],[filter3],...</code> -- <code>[object]</code> is now the central location to check for farthest entity, ignored entities can be a target.</p>