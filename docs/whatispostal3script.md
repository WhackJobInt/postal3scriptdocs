# What is Postal3Script?

Postal3Script, or P3S, is a Finite State Machine (FSM) and a scripting language developed for Postal 3, designed to handle most of the NPC AI and mission scripting.

It allows for a much easier and faster time doing missions and AI rather than messing around in C++ and doing logic entirely through map entities in Hammer.

With Postal3Script, you can easily do many things that you normally would not be able to do without the source code of the game due to the many useful functions and attributes that are interfaced.

While Postal3Script is a scripting language, it is not as powerful as say, Garry's Mod's LUA, it is heavily limited by the amount of functions available, it's also unfortunately not as fast as LUA in execution speed.

P3S script files are located in <code>Postal III/p3/scripts</code> and use the <code>.p3s</code> file extension, but it can be any extension if wanted. To load and be able to use a p3s script, you must add it to a manifest, in "ai_scripts.txt", found in the previously mentioned folder.

<a href="../zips/scripts.zip">HERE</a> you can download the contents of Postal 3's scripts folder, if you need it for researching purposes, or just out of curiosity.

!!! tip "Tip"

    Changes to p3s scripts will automatically hotload when the map changes, so you can just use the `restart` console command without ever having to exit and reload the game.
	
    It is highly recommended to snoop around the game files and find examples of what you're trying to accomplish to get a better idea of the language.

## Postal3Script Example

```js
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
```

## Limitations

!!! warning "Limitations"

    Postal3Script comes with limitations. Ignoring these limitations will make your script behave oddly, and unexpectedly:
	
    * In Postal3Script, Attributes can only be whole numbers/integers, attributes can't be floats, doubles, or strings.  
	However, the <code>Wait</code> and <code>Repeat</code> functions are the only exception where you can freely use floats.
		* An Attribute must have a value initialized before checking it's value using <code>CheckAttr</code>, meaning an attribute that doesn't exist will never return a valid value.  
		(Checking if it's zero/null doesn't work).<br>

	* Extremely sensitive to spaces when using parameters for functions, this can lead to unexpected behavior.
	<br><br>
	* Errors in a script file won't show up without enabling a console command first, and most of the time it's not obvious if the code is working fine.
	<br><br>
	* Postal3Script function names are case-sensitive, i.e. it's not recommended to use <code>ifattr</code> instead of <code>IfAttr</code>.
	<br><br>
	* Very long code can (sometimes) result in the game freezing, this can be avoided by splitting up the patterns.
	