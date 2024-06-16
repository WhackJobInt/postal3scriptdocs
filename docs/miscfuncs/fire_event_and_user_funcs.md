# Fire And Event Functions

## FireEvent
<p>Fire an FSM script event.</p>

<h2>Syntax</h2>
<p><code class="language-js">FireEvent [eventname]</code> -- Fire an event with this name</p>
<p><code class="language-js">FireEvent [eventname],[destinationtype]</code> -- Fire an event with this name and destination type</p>

<div class="admonition warning">
<p class="admonition-title">Warning</p>
<p>You must have the <code>OnFire_</code> prefix before the actual function name of your event when you declare it! For example: <code>OnFire_EventFireTest</code></p>
<p>When firing events, you only use the name of the function, without the "OnFire_" prefix!</p>
<p>The events that you fire are dependant on the targeted entity!</p>
<p>Despite being pretty global otherwise, keep in mind that the events you fire are destination specific! Make sure to target the correct entities!</p>
</div>

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Here's a list of all the destination types:
<code>owner, target, caller, player, point, anchor, slot, self</p></code>
<p>It doesn't matter what state, pattern, or behaviour the event is declared in</p>
<p>Note that even if you want the action block empty, in order to declare event functions, you must have an empty one anyway!
<p>This is basically the equivalent of the <code>FireFSMScriptEvent</code> entity output
</div>

<div class="admonition tip">
<p class="admonition-title">Tip</p>
<p>You can fire events from entirely seperate entities without inheritance by doing <a href="../../targetingfuncs/targetentbyname/">TargetEntByName</a> before you fire them!
</p>

</div>

<h2>Example</h2>
<pre><code class="language-js">
st_state1
{
	Group Alert
	Patterns
	{
		pt_default
		{
			actions
			{
				SetAttr "Test 0"

				// When firing events, you only use the name 
				// of the function, without the "OnFire_" prefix!
				FireEvent EventFireTest
			}
		}
	}
}

st_state2
{
	Group Neutral
	Patterns
	{
		pt_default
		{
			// Note that even if you want the action block empty, in order 
			// to declare event functions, you must have an empty one anyway!
			actions
			{
				
			}
			events
			{
				// Make sure you have the "OnFire_" prefix in your event function name!
				OnFire_EventFireTest "ChangeAttr Test +1"
			}
		}
}


</code></pre>

<br>
## FireEventEx

<p>Unused Postal3Script function.</p>

<p>The same as <a href="#fireevent">FireEvent</a>, except it only checks for the <code>self</code> destination type parameter, otherwise it will default to <code>target</code>.</p>

<div class="admonition warning">
<p class="admonition-title">Warning</p>
<p>Only the <code>self</code> destination type parameter is allowed!</p>
</div>

<h2>Syntax</h2>
<p><code class="language-js">FireEventEx [eventname]"</code> -- Fire an event on the targeted entity</p>
<p><code class="language-js">FireEventEx [eventname],self"</code> -- Fire an event with this name with the <code>self</code> destination type</p>

<h2>Example</h2>
<pre><code class="language-js">
pt_default
{
	actions
	{
		TargetEntByName scary_npc // Target the npc

		// If the target is close enough to us, fire the GetScared event on ourself!
		IfAttr "DistTo:target < 50 FireEventEx GetScared,self"
		
		// Otherwise if our target is far away from us, fire the
		// CantFindScaredyCat event on our target!
		IfAttr "DistTo:target > 150 FireEventEx CantFindScaredyCat"
	}
}
</code></pre>

<br>

## FireUser

Fire user entity inputs set through Hammer on the entity.

!!! warning "Warning"
	Activator and the Caller will be the entity itself.

### Syntax
<p><code class="language-js">FireUser 1</code> -- Fire the slot 1 input</p>
<p><code class="language-js">FireUser 2</code> -- Fire the slot 2 input</p>
<p><code class="language-js">FireUser 3</code> -- Fire the slot 3 input</p>
<p><code class="language-js">FireUser 4</code> -- Fire the slot 4 input</p>

<br>

## EntFireUser

Fire user entity inputs set through Hammer on a named entity.

!!! warning "Warning"
	Activator and the Caller will be the entity itself (the one that called the function).
	
### Syntax
<p><code class="language-js">EntFireUser [ent_name],1</code> -- Fire the slot 1 input on the entity</p>
<p><code class="language-js">EntFireUser [ent_name],2</code> -- Fire the slot 2 input on the entity</p>
<p><code class="language-js">EntFireUser [ent_name],3</code> -- Fire the slot 3 input on the entity</p>
<p><code class="language-js">EntFireUser [ent_name],4</code> -- Fire the slot 4 input on the entity</p>

<br>

## FireInput

Fire entity inputs on an entity.  
You can see [here](../inputfunctions.md) the list of all available inputs.

!!! warning "Warning"
	Only <code>self</code> and <code>target</code> are supported.
	
### Syntax

<code>FireInput target,[input]</code> -- Fires input on the entity's target.

<code>FireInput self,[input]</code> -- Fires input on the entity.

<br>

## EntFireInput

Fire entity inputs on a named entity.  
You can see [here](../inputfunctions.md) the list of all available inputs.  
Radius is always checked from the executed entity.
	
### Syntax

<code>EntFireInput [name],[input]</code> -- Fires input on the named entity.

<code>EntFireInput [name],[input]:[param]</code> -- Fires input with param (if supported) on the named entity.

<code>EntFireInput [name],[input],[radius]</code> -- Fires input on the named entity if it's around the radius.

<code>EntFireInput [name],[input]:[param],[radius]</code> -- Fires input with param (if supported) on the named entity if it's around the radius.

<br>

## OnUser (Events)

Fire user entity outputs set through Hammer on a specific entity.  
When they are invoked, they can call a Postal3Script event.

Only up to 4 are supported. <code>OnUser1</code> -> <code>OnUser4</code>