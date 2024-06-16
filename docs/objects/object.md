# Object Entities

## Object
An object, such as an NPC, Player or a prop.

In Postal3Script you have access to certain objects such as `target` or the behavior's host, and you can either manipulate or read from them.

You don't always have access to the `caller`, as it's heavily dependent on the Event that caused the Object to enter the pattern.

Typically, the caller means something or someone that forced the Object to enter a pattern.

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>All the objects in Postal3Script:</p>
<p><code>Object:Caller</code> ; <code>Object:Target</code> ; <code>Object:Player</code></p>
<p><code>Object:slot#0</code> ; <code>Object:null</code> ; <code>Object:self</code></p>
<p><code>Object:item</code> ; <code>Object:anchor</code> ; <code>Object:destination</code></p>
</div>

!!! tip "🪽 Postal 3 Angel-only feature"
	- `Object:item` on Players behaves the same like with NPCs.
	- `Object:item` can be used to get the active weapon, including dismembered bodyparts and throwable objects on Players and NPCs.

<h1>Syntax</h1>
<p><code class="language-js">Object:[object]</code> -- Returns the Object specified</p>
<h1>Example</h1>
<pre><code class="language-js">
// Check if our caller exists (null == zero)
IfAttr "Object:caller != Object:null Block Begin"
	// Was it the Player who forced us into this state?
	IfAttr "Object:caller == Object:player Block Begin"
		// Well then we are going to run to them endlessly
		TargetPlayer 1 // or TargetCaller 1
		MoveToTarget run,1,0
	Block End
Block End

// Check if our target isn't the Player
IfAttr "Object:target != Object:null and Object:target != Object:Player Block Begin"
	// Bad day for our enemy, though, because they are going to die instantly
	ChangeAttr "target.ea_health -target.ea_health"
Block End

// Object:self and Object:item are barely used, the latter is used by Motorhead
// It's a pointer to the NPC's held item
// Check out ai_motorhead.p3s, ai_st1_common.p3s, ai_st2_states.p3s 
// and ai_st7_environment.p3s

</code></pre>
<br>
## Saving Objects To Memory
<p>You are capable of saving an object to memory, with up to 10 slots.
<p>This feature is typically used for keeping track of progress on tasks and related to mission logic.
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>The '6' and '7' memory slot was never used. Cannot be higher than 10 or lower than 0.</p>
</div>

<h1>Example</h1>
<pre><code class="language-js">
// (from ai_st_init.p3s)
// Const msTEMP,0
// Const msOWNER,1
// Const msTARGET,2
// Const msENEMY,3
// Const msSUSPECTED,4
// Const msLEADER,5
// Const msDRIVEN,6
// Const msINTEREST,7
// Const msKILLER,8
// Const msGP,9

// Get entity named 'gameplay' and set it as target
TargetEntByName gameplay

// Save the target to memory
TargetToMem msGP

// Set the MathLogic's attribute
ChangeAttr "slot#msGP.MoneyGiven +5"

// Reset the target
ResetTarget 1
</code></pre>