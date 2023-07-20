## GetGibbedLimbs

<p>A function which checks how much the NPC was sliced up, and creates/updates <code>ea_gibbed</code> accordingly.</p>

<div class="admonition warning">
<p class="admonition-title">Catharsis Reborn Feature</p>
<p>The following function will only work in <b>Catharsis Reborn</b>.</p>
</div>

<h1>Syntax</h1>
```
// ea_gibbed
Const CORPSE_LIMB_ALL,0 // has all limbs attached
Const CORPSE_LIMB_ALL_HEAD,1 // head is missing

Const CORPSE_LIMB_HEAD,254
Const CORPSE_LIMB_LEFTARM,247
Const CORPSE_LIMB_RIGHTARM,239
Const CORPSE_LIMB_LEFTLEG,253
Const CORPSE_LIMB_RIGHTLEG,251
Const CORPSE_LIMB_UPPERBODY,127
Const CORPSE_LIMB_LOWERBODY,191
```

`GetGibbedLimbs 1` -- Creates or updates `ea_gibbed` attribute if it was called on a corpse entity.

<div class="admonition note">
<p class="admonition-title">Note</p>
<p><code>ea_gibbed</code> will also update if the entity was "hurt", or sliced up even more.</p>
</div>

<h1>Example</h1>
```{ .lang linenos=true }
// This pattern will loop until the attribute was successfully created
pt_initGibbed
{
	actions
	{
		Wait 1
		
		SetAttr "exists 0"
		CheckAttr "ea_gibbed SetAttr exists 1"
		IfAttr "exists == 0 Block begin"
			GetGibbedLimbs 1
		Block end
		
		IfAttr "exists == 1 BLock begin"
			RemoveAttr exists
			Pattern pt_loop
		Block end
		
		Repeat 0
	}
}

// This checks if the corpse entity is a single limb
xpt_singleLimbCheck
{
	actions
	{
		SetAttr "cr_singleLimb 0"
		
		IfAttr "ea_gibbed == CORPSE_LIMB_HEAD 		SetAttr cr_singleLimb 1"
		IfAttr "ea_gibbed == CORPSE_LIMB_LEFTARM 	SetAttr cr_singleLimb 1"
		IfAttr "ea_gibbed == CORPSE_LIMB_RIGHTARM 	SetAttr cr_singleLimb 1"
		IfAttr "ea_gibbed == CORPSE_LIMB_LEFTLEG 	SetAttr cr_singleLimb 1"
		IfAttr "ea_gibbed == CORPSE_LIMB_RIGHTLEG 	SetAttr cr_singleLimb 1"
		IfAttr "ea_gibbed == CORPSE_LIMB_UPPERBODY 	SetAttr cr_singleLimb 1"
		IfAttr "ea_gibbed == CORPSE_LIMB_LOWERBODY 	SetAttr cr_singleLimb 1"
	}
}
```