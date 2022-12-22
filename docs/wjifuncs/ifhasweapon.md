## IfHasWeapon

<p>Conditional function which checks if object has a weapon stored.</p>

<div class="admonition warning">
<p class="admonition-title">Catharsis Reborn Feature</p>
<p>The following function will only work in <b>Catharsis Reborn</b>.</p>
</div>

<h1>Syntax</h1>
```
// from AI_CR_WeaponID.p3s

// Engine attributes to use with Weapons:
// weapon_twohanded (automatically determined)
// weapon_id
// weapon_type

// Limbs
Const LIMB_LEFTARM,4
Const LIMB_RIGHTARM,5
Const LIMB_LEFTLEG,6
Const LIMB_RIGHTLEG,7

// Weapon type (weapon_type)
Const WPN_MELEE,1
Const WPN_GUN,2
Const WPN_SPRAY,3
Const WPN_NADE,4
Const WPN_LIMB,5

// Weapon ID ('weapon_id' [Weapons] || 'ea_armed' [NPCs])
Const WPN_INVALID,0		// Animals do not use any kind of weapon, so 'ea_armed' is always zero for them
Const WPN_NONE,1 		// P3_WEAPON_EMPTYHANDS
Const WPN_BADGER,2		// P3_WEAPON_WOLVERINE
Const WPN_NAILBAT,3		// P3_WEAPON_NAILBAT
Const WPN_GRENADE,4		// P3_WEAPON_GRENADE
Const WPN_DEGL,5		// P3_WEAPON_DESERT_EAGLE (Can shoot off limbs)
Const WPN_TASER,6		// P3_WEAPON_TASER
Const WPN_SHTG,7		// P3_WEAPON_SHOTGUN (Can shoot off limbs)
Const WPN_M60,8			// P3_WEAPON_M60 (Can shoot off limbs)
Const WPN_M16,9			// P3_WEAPON_M16 (Can shoot off limbs)
Const WPN_CATS,10		// P3_WEAPON_CAT
Const WPN_MACHETE,11	// P3_WEAPON_MACHETE (Can shoot off limbs)
Const WPN_SHOVEL,12		// P3_WEAPON_SHOVEL
Const WPN_MOLOTOV,13	// P3_WEAPON_MOLOTOV
Const WPN_GAS,14		// P3_WEAPON_GASOLINE
Const WPN_CATNIP,15		// P3_WEAPON_CATNIP
Const WPN_BANNER,16		// P3_WEAPON_BANNER
Const WPN_BEES,17		// P3_WEAPON_BEENEST
Const WPN_BATON,18		// P3_WEAPON_COP_BATON
Const WPN_KDOLL,19		// P3_WEAPON_KROTCHY_GRENADE
Const WPN_HAMMER,20		// P3_WEAPON_HAMMER
Const WPN_LASER,21		// P3_WEAPON_LASERPEN
Const WPN_MATCH,22		// P3_WEAPON_MATCH
Const WPN_MAXEL,23		// P3_WEAPON_MAXEL_SNIPER (this weapon doesn't exists)
Const WPN_BULKY,24		// P3_WEAPON_METABULKY
Const WPN_ONEHAND,25	// P3_WEAPON_METAONEHANDLED
Const WPN_TWOHAND,26	// P3_WEAPON_METATWOHANDLED
Const WPN_MONKEY,27		// P3_WEAPON_MONKEY
Const WPN_CAM,28		// P3_WEAPON_PHOTOCAM
Const WPN_SEED,29		// P3_WEAPON_SEED
Const WPN_SHOPVAC,30	// P3_WEAPON_SHOPVAC
Const WPN_SPRAY,31		// P3_WEAPON_SPRAY
Const WPN_TVCAM,32		// P3_WEAPON_TVCAM
Const WPN_WEEMOTE,33	// P3_WEAPON_WEEMOTE
Const WPN_LAUNCHER,34	// P3_WEAPON_M136
Const WPN_AXE,35		// P3_WEAPON_FIREAXE (Can shoot off limbs)
Const WPN_GAMAMET,36	// P3_WEAPON_GAMAMET
Const WPN_GLOCK17,37	// P3_WEAPON_GLOCK17
Const WPN_REVOLVER,38	// P3_WEAPON_REVOLVER (Can shoot off limbs)
Const WPN_TTPISTOL,39	// P3_WEAPON_TTPISTOL
Const WPN_AK47,40		// P3_WEAPON_AK47 (Can shoot off limbs)
Const WPN_P90,41		// P3_WEAPON_P90

Const WPN_CRSHOT,43		// CR_WEAPON_SHOTGUN (Can shoot off limbs)
Const WPN_M249,44		// P3_WEAPON_M249 (Can shoot off limbs)
Const WPN_AWP,45		// P3_WEAPON_AWP (Can shoot off limbs)

Const WPN_DEBUGPEN,47	// CR_WEAPON_DEBUGPEN
Const WPN_FLASH,48		// CR_WEAPON_FLASH_GRENADE
Const WPN_DOGTOY,49		// CR_WEAPON_DOGTOY
```

`IfHasWeapon "Object:<obj> <weaponid> <action>` -- Checks if `Object:<obj>` has `<itemid>` stored in their inventory.</p>

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>If used against the Player, it will also check if they have enough ammo to use the weapon, even if they technically own the weapon, if they do not have any ammo the check automatically fails.
Melee weapons do not have ammo checking.</p>
</div>

<h1>Example</h1>
```
// Example code
xpt_example
{
	actions
	{
		IfHasWeapon "Object:player WPN_DOGTOY Pattern pt_gimme"
		
		IfHasWeapon "Object:player WPN_SHOPVAC Pattern pt_spawnwads"
		
		IfAttr "Object:target != Object:player Block begin"
			IfHasWeapon "Object:target WPN_BATON Pattern pt_brutality"
		Block end
		
		IfHasWeapon "Object:self WPN_MACHETE Block begin"
			Weapon arm
			Wait 1
			Weapon drop
		Block end
	}
}
```