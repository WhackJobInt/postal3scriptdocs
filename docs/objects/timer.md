# Timer
<p>Creates a timer to wait before executing an event.
<h1>Syntax</h1>
<p><code class="language-js">Timer [string],[float]</code> -- Creates a Timer, will execute <code>OnTimer_[string]</code> event after <code>[float]</code> seconds.</p>
<p><code class="language-js">Timer [string],[float],repeatable</code> -- Creates a Timer, will execute <code>OnTimer_[string]</code> event after every <code>[float]</code> seconds.</p>
<p><code class="language-js">Timer [string],0</code> -- Disables a Timer completely.</p>
<p><code class="language-js">Timer:[string]</code> -- Get a Timer object's timer/value.</p>

<div class="admonition warning">
<p class="admonition-title">Warning</p>
<p>Checking for a non-existent Timer is not possible. You must pre-create all the timers you will use with <code>Timer [string],0</code> to ensure <code>IfAttr</code> will properly return zero value.</p>
<p>The example below shows a piece of code that will always fail if <code>tCantHeal</code> doesn't exists, and instead of returning from it, it will continue to execute all the actions below it.
</div>

<pre><code class="language-js">
// This state was entered from somewhere else...
st_medic
{
	Group Neutral
	Patterns
	{
		pt_default
		{
			actions
			{
				// We assume that 'tCantHeal' is a global timer set somewhere else...
				// (Note: if 'tCantHeal' does not exist, this check will fail and will continue 
				// to create 'tHealMe' timer)
				IfAttr "Timer:tCantHeal > 0 Block begin"
					State st_canthealmyself
					Return 0
				Block end
				
				// If we somehow want to limit this NPC to only fully regenerate once...
				IfAttr "fullyregenerated == 1 Block begin"
					State st_canthealmyself
					Return 0
				Block end
				
				Timer tHealMe,3,repeatable
			}
			events
			{
				// Will execute after every 3 seconds
				// (only pt_default will be able to see this event)
				OnTimer_tHealMe	"Pattern pt_healcheck"
			}
		}
		
		pt_healcheck
		{
			actions
			{
				// If our health is equal to or greater than 100 don't bother healing ourselves
				IfAttr "ea_health >= 100 Block begin"
					// Disable the timer
					Timer tHealMe,0
					State st_start // enter into another state...
					SetAttr "fullyregenerated 1"
					Return 0
				Block end
				
				ChangeAttr "ea_health +5"			
				Pattern pt_default
			}
		}
	}
}

//
// Alternative version, which instantly heals an NPC after a few seconds...
//
st_godmode
{
	Group Neutral
	Patterns
	{
		pt_default
		{
			actions
			{	
				Timer tGod,7
			}
			events
			{
				// Will execute after 7 seconds
				// (only pt_default will be able to see this event)
				OnTimer_tGod	"Pattern pt_miracle"
			}
		}
		
		pt_miracle
		{
			actions
			{	
				SetAttr "ea_health 100"
				State st_start
			}
		}
	}
}
</code></pre>