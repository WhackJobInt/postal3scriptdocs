# Randomization
Randomization in Postal3Script is very straightforward.

!!! tip "Random"
    The <code>:</code> symbol always mean randomization.  
	(There are a few exceptions, but usually it is always *random* when used with values)
	
	<code>[min]:[max]</code> or <code>[max]:[min]</code> is the syntax for this.
	
	There's a slight 'bias' when randomizing, for example a randomization from 4 to 9 **won't** be   
	exactly 4:9, but could be also 3:10 
	
	That's why it's recommended not to check for **exact** value, but to check if they are higher or lower than the value.
	
## Examples

```js
pt_example
{
	actions
	{
		// Randomizes waiting (works with floats too!)
		Wait 0.5:9.5
		
		// Randomizes repeat (also works with floats!)
		Repeat 1:4.5
		
		SetAttr "rnd 0"
		// Randomizes attribute
		ChangeAttr "rnd 0:100"
		
		// You can also randomize an attribute this way
		SetAttr "rnd 50:100"
		
		// Randomizes timer
		Timer tTest,5:7,repeated
		
		// Randomizes gesture
		Gesture g_emote_afraid,15:3
		
		// Randomizes looking
		LookAt 5:10
		
		// Randomizes moving to the target
		MoveToTarget run,1.5:3.5
		
		// Randomizes turning
		Turn 90:270
		
		// Randomizes sequence's time
		Sequence seq.reaction_shocked,seq.reaction_shocked_2,2:5
	}
}
```