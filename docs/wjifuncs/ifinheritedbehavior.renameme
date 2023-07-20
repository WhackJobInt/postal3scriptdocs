## IfInheritedBehavior

<p>Checks if an entity's inherited behavior is equal to this condition.</p>

<div class="admonition warning">
<p class="admonition-title">Catharsis Reborn Feature</p>
<p>The following function will only work in <b>Catharsis Reborn</b>.</p>
</div>

<h1>Syntax</h1>
```{ .lang linenos=true }
IfInheritedBehavior "<behavior to check against> Block begin"
	// do stuff
Block end
```

<h1>Example</h1>
```{ .lang linenos=true }
// Assuming this is in bh_npc_base (and the state doesn't exists in other behaviors, so they won't override this)
st_corpse
{
	Group Alert
	Patterns
	{
		pt_default:ignore_ext_events
		{
			actions
			{
				SetAttr "ea_status sCORPSE"
				
				// First let's check if our behavior is exactly bh_npc_police
				IfBehavior "bh_npc_police Block begin"
					SetBehavior "bh_item_corpse_cop,itm_limb,itm_limb,Corpse,itmLimb"
					Return 1
				Block end
				
				// Okay, not bh_npc_police, but maybe we inherited from it?
				IfInheritedBehavior "bh_npc_police Block begin"
					SetBehavior "bh_item_corpse_cop,itm_limb,itm_limb,Corpse,itmLimb"
					Return 1
				Block end
				
				SetBehavior "bh_item_corpse,itm_limb,itm_limb,Corpse,itmLimb"
			}
		}
	}
}
```