# What is Postal3Script?

Postal3Script, or P3S, is a Finite State Machine (FSM) and a scripting language developed for Postal 3, designed to handle most of the NPC AI and mission scripting.

It allows for a much easier and faster time doing missions and AI rather than messing around in C++ and doing logic entirely through map entities in Hammer.

With Postal3Script, you can easily do many things that you normally would not be able to do without the source code of the game due to the many useful functions and attributes that are interfaced.

P3S script files are located in <code>Postal III/p3/scripts</code> and use the <code>.p3s</code> file extension, but it can be any extension if wanted. To load and be able to use a p3s script, you must add it to a manifest, in "ai_scripts.txt", found in the previously mentioned folder.

<div class="admonition tip">
<p class="admonition-title">Tip</p>
<p>Changes to p3s scripts will automatically hotload when the map restarts, so you can just use the "restart" console command without ever having to exit and reload the game.</p>
<p>It is highly recommended to snoop around the game files and find examples of what you're trying to accomplish to get a better idea of the language.</p>
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
<li>In Postal3Script, Attributes can only be whole numbers/integers, attributes can't be floats, doubles, or strings. However, the <code>Wait</code> and <code>Repeat</code> functions are the only exception where you can freely use floats.</li>
<br>
<li>An Attribute must have a value initialized before checking it's value using <code>CheckAttr</code>, meaning an attribute that doesn't exist will never return a valid value. (Checking if it's zero/null doesn't work).</li>
<br>
<li>Extremely sensitive to spaces when using parameters for functions, this can lead to unexpected behavior.</li>
<br>
<li>Errors in a script file won't show up without enabling a console command first, and most of the time it's not obvious if the code is working fine.</li>
<br>
<li>Postal3Script function names are case-sensitive, i.e. it's not recommended to use <code>ifattr</code> instead of <code>IfAttr</code>.</li>
</ul>
</div>
<br>