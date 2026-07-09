## IfCurGroup

<p>Checks if the entity's current state's group matches this condition.</p>

<div class="admonition warning">
<p class="admonition-title">Postal III Ultrapatch+Angel v1.3.0+ Feature</p>
<p>The following function will only work in <b>Postal III Ultrapatch+Angel v1.3.0 or higher</b>.</p>
</div>

<h1>Syntax</h1>
```
IfCurGroup "Neutral Block begin"
	...
Block end

IfCurGroup "Alert Block begin"
	...
Block end

IfCurGroup "Combat Block begin"
	...
Block end
```

<h1>Example</h1>

```
// Check if the NPC is not in combat
xpt_checkCombat
{
	actions
	{
		IfCurGroup "Neutral Block begin"
			State st_eatfood
		Block end
	}
}

st_eatfood
{
	Group Neutral
	Patterns
	{
		pt_default
		{
			actions
			{
				Inventory select,ITM_PIZZA
				IfAttr "Object:inventory != Object:null Block begin"
					Inventory equip
					Pattern pt_eat
				Block end
				
				State st_idle
			}
		}
		
		pt_eat
		{
			actions
			{
				...
			}
		}
	}
}
```