# What is Postal3Script?

<p>Postal3Script, or P3S, is a scripting language developed for Postal 3, designed to handle most of the NPC AI and mission scripting.
It allows for a much easier and faster time doing missions and AI rather than messing around in C++ and doing logic entirely through map entities in Hammer.
<p>With Postal3Script, you can easily do many things that you normally would not be able to do without the source code of the game due to the many useful functions and attributes that are interfaced.
<p>P3S script files are located in "/Postal III/p3/scripts" and use the ".p3s" file extension. To load and be able to use a p3s script, you must add it to a manifest, in "ai_scripts.txt", found in the previously mentioned folder.
<p>Changes to p3s scripts will automatically hotload when the map restarts, so you can just use the "restart" console command without ever having to exit and reload the game.
<p>It is highly recommended to snoop around the game files and find examples of what you're trying to accomplish to get a better idea of the language.

<h2>Postal3Script Example</h2>
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
<h1> Limitations </h1>
<p>Each state can hold events, which in turn can execute patterns. Patterns can be inherited from other P3S actors, as well as Attributes.
<p>* In Postal3Script, Attributes can only be whole numbers/integers, attributes can't be floats, doubles and strings.
<p>* An Attribute must have a value initialized before checking it's value using CheckAttr, meaning an attribute that doesn't exist will never return a valid value. (Checking if it's zero/null doesn't work).
<p>* You can only have a limited number of if statements in a single state or pattern.
<p>* An Attribute can only have a maximum of '100' value
<p>* Sensitive to spaces when using functions

<h1> Debugging code </h1>
<p>Normally the game doesn't print out any errors, you need to have the "developer" and "p3_fsm_spew" console commands enabled.</p>
<p>Scrolling around in the console should show you which script and what lines have errors if there are any.
<p>If you want to print out your own debug messages, You'll have to settle for doing EntFireInput on the point_clientcommand in the map via "EntFireInput pcc,Command: echo yourmessagehere". Debug channel specific ShowMessages are broken it seems.

<h1> Unused Postal3Script files </h1>
<p>Trashmasters have left many p3s scripts that were used during the development of Postal III just sitting around.
<p>Many of them contain cut features, unused logic, and various tests.
<pre><code class="language-js">
'ai_badger_test.p3s' - Badger testing
'ai_cashmart.p3s' - Earlier version of Cashmart (ai_cashmart_npc.p3s is not unused)
'ai_gameplay.p3s' - Intended for Open World gameplay
'ai_patrol1_citizen_fight.p3s' - Unknown
'ai_st1_common.p3s' - Contains various old code
'ai_st2_states.p3s' - Contains various old code
'ai_st3_social.p3s' - Contains experimental old code
'ai_st4_queuie.p3s' - Queue testing
'ai_st5_temp.p3s' - Contains test code, scrapped features
'ai_st6_missions.p3s' - Test code related to missions
'ai_st7_environment.p3s' - Code related to cut environment behavior
'ai_st8_items.p3s' - Code related to cut inventory items
'ai_st9_animals.p3s' - Animals test
'ai_st10_temp.p3s' - Test script, contains code related to Traffic lights
'ai_st11_urza.p3s' - Contains scrapped features, old code
'ai_st12_urza.p3s' - Contains scrapped features, old code
'ai_st98_helicopter.p3s' - Code that's identical to today's Helicopter AI
'ai_st_utilities.p3s' - Various code related to NPCs
'ai_test_babuska.p3s' - Test script
'lean_test.p3s' - Test script
</code></pre>