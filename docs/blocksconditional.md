# Blocks, Conditional
In Postal3Script instead of brackets, you use blocks, this is similar to how LUA does it.

!!! tip "Rules"
    A block always *begins* with <code>Block begin</code> and *ends* with <code>Block end</code>  
	
	Functions that support Blocks in conditionals:  
	- <code>IfAttr</code>  
	- <code>CheckAttr</code>

!!! warning "TODO (?)"
	Block seem to support <code>Execute</code>, what does it actually do?  
	Begins with `Block Begin,Execute` and ends with `Block End`, in between can be placed code.  
	Is it still working or is it a remnant from the past?  
	Note this is only found in test scripts left by TM devs, it's not in any release scripts.

## Examples

```js
pt_example
{
	actions
	{
		// Let's randomize this attribute from 0 to 100..
		SetAttr "rnd 0:100"
		
		// AND Keyword can be useful here too!
		IfAttr "rnd < 9 AND ea_health < 100 Block begin"
			// Code below will never run because we enter into another pattern.
			Pattern pt_secret
		Block end
		
		// You can also use blocks with CheckAttr
		CheckAttr "myspecialattribute Block begin"
			SetAttr "rnd 45:100"
		Block end
		
		// Let's check if it's higher than 50
		// Pay attention to the block function!
		IfAttr "rnd > 50 Block begin"
			// Now here press tab once and start putting code in here!
			SetAttr "rnd 50:100"
			
			// By putting 'Return 1' here, this will return from the entire pattern!
			// Code below will never execute!
			Return 1
		Block end
		
		// It wasn't over 50... so let's just enter another pattern.
		Pattern pt_fail
	}
}
```

You can also put blocks inside blocks, but sooner or later it'll be a mangled spaghetti.

```js
// from ai_mission_bdk.p3s, snipped
pt_example
{
	actions
	{	
		IfAttr "TaskCombat == TC_SHOOT Block begin"
			IfAttr "TaskLogicPath < 7 Block begin"
				Timer tTaskCombat,5:5
				IfAttr "ThrownGrenade < MAX_LIVE_GRENADE SetAttr TaskCombat TC_THROW"
				IfAttr "ThrownGrenade >= MAX_LIVE_GRENADE SetAttr TaskCombat TC_MOVETO"
			Block end
			IfAttr "TaskLogicPath >= 7 Block begin"
				Timer tTaskCombat,3:2
				SetAttr "TaskCombat TC_MOVETO"
			Block end
		Block end
	}
}
```