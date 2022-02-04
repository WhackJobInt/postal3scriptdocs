# What is Postal3Script?

Postal3Script, or P3S, is a scripting language developed for Postal 3, designed to handle most of the NPC AI and mission scripting.

It allows for a much easier and faster time doing missions and AI rather than messing around in C++ and doing logic entirely through map entities in Hammer.

With Postal3Script, you can easily do many things that you normally would not be able to do without the source code of the game due to the many useful functions and attributes that are interfaced.

P3S script files are located in <code>/Postal III/p3/scripts</code> and use the <code>.p3s</code> file extension. To load and be able to use a p3s script, you must add it to a manifest, in "ai_scripts.txt", found in the previously mentioned folder.

It is highly recommended to snoop around the game files and find examples of what you're trying to accomplish to get a better idea of the language.

<div class="admonition tip">
<p class="admonition-title">Tip</p>
<p>Changes to p3s scripts will automatically hotload when the map restarts, so you can just use the "restart" console command without ever having to exit and reload the game.</p>
</div>

## Postal3Script Example

<pre><code class="language-js">
Constants
{
	Const DONUTS_INCR,1
	Const SOMEBODY_STOLE_MY_DONUTS,15
	Const YES,1
	Const NO,0
}

behavior
{
	name bh_evensuperioractor
	inherited bh_mysuperioractor
	
	States
	{
		st_mycustomstate
		{
			Group Alert
			Patterns
			{
				pt_default
				{
					// Only executes when on Alert
				}
			}
		}
		
		st_nowyallgonnapay
		{
			Group Combat
			Patterns
			{
				pt_default
				{
					// Only executes when in Combat
					SetAttr	"veryverypissedoff YES"
					Pattern pt_donuts
				}
				
				pt_donuts
				{
					IfAttr "veryverypissedoff == YES Pattern st_nowyallgonnapay.pt_allgood"
				}
				
				pt_allgood
				{
					SetAttr	"veryverypissedoff NO"
				}
			}
		}
		events
		{
			OnDeath "ExecutePattern st_OnDeath.pt_default"
			OnTimer_tUnstun	"Pattern pt_end"
			OnUnconscious "Pattern pt_unconscious"
			OnHostaged "Pattern pt_hostaged"
			OnSprayStunned "Timer tUnstun,SPRAY_UNSTUN_TIMER"
			OnTimer_tScream "ExecutePattern .xpt_SayScream"
			OnUnstunned "Pattern pt_end"
			OnStandUpEnd "Pattern pt_end"
		}
		
		// Sets on spawn
		st_init
		{
			Group Neutral
			Patterns
			{
				pt_default
				{
					actions
					{
						Senses false
					}
				}
			}
		}
		
		// Called continously
		st_start
		{
			Group Neutral
			Patterns
			{
				pt_default
				{
					actions
					{
						// tick
					}
				}
			}
		}
	}
}
</code></pre>

## Limitations
<div class="admonition warning">
<p class="admonition-title">Warning</p>
<p id="limitations">Postal3Script comes with limitations. Ignoring these limitations will make your script behave oddly, and unexpectedly.</p>
<ul>
<li>In Postal3Script, Attributes can only be whole numbers/integers, attributes can't be floats, doubles and strings. <code>Wait</code> and <code>Repeat</code> is the only exception in this case, where you can freely use floats.</li>
<li>An Attribute must have a value initialized before checking it's value using CheckAttr, meaning an attribute that doesn't exist will never return a valid value. (Checking if it's zero/null doesn't work).</li>
<li>You can only have a limited number of if statements in a single state or pattern. It's not entirely clear why it breaks.</li>
<li>An Attribute can only have a maximum of '100' value.</li>
<li>Sensitive to spaces when using parameters for functions.</li>
</ul>
</div>

## Debugging code
<p>Normally the game doesn't print out any errors, you need to have the "developer" and "p3_fsm_spew" console commands enabled.</p>
<p>Scrolling around in the console should show you which script and what lines have errors if there are any.
<p>If you want to print out your own debug messages, You'll have to settle for doing EntFireInput on the point_clientcommand in the map via "EntFireInput pcc,Command: echo yourmessagehere". Debug channel specific ShowMessages are broken it seems.