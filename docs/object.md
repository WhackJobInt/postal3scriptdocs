# Object
<p>In Postal3Script you have access to certain pointers which helps you with targeting the correct actor.
<pre><code class="language-js">
// In P3S you can check for the following objects:
// 'Object:Caller' ; 'Object:Target' ; 'Object:Player'
// 'Object:slot#0' ; 'Object:null' ; 'Object:self'
// 'Object:item' ; 'Object:anchor'

// You don't always have a pointer to the Caller, as it's
// heavily dependent on the Event which caused the NPC to enter this state
// Meaning, there's something or someone that forced the NPC to enter this state

// Check if our caller exists (null means zero)
IfAttr "Object:caller != Object:null Block Begin"
	// Was it the Player who forced us into this state?
	IfAttr "Object:caller == Object:player Block Begin"
		// Well then we are going to run to them, endlessly
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

// Object:anchor is used only in ai_mission_jwb.p3s (todo: what the hell it is?)
</code></pre>
<h1>Memory Objects</h1>
<p>An actor is capable of saving a pointer to memory, up to 10 slots.
<p>It's mostly used for mission making, counting, or logic in Postal III.
<p>6 and the 7 memory slot was never used by Trashmasters. It cannot be higher than 10 or lower than 0.
<pre><code class="language-js">
// (from ai_st_init.p3s)
// Const msTEMP,0
// Const msOWNER,1
// Const msTARGET,2
// Const msENEMY,3
// Const msSUSPECTED,4
// Const msLEADER,5
////Const msDRIVEN,6
////Const msINTEREST,7
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