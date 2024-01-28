# States, Patterns, Execute Patterns
States, Patterns, and Execute Patterns are the very main core of Postal3Script, these make up 100% of all scripts, and they are essentially the "AI".

!!! tip "States, Patterns, and Execution Patterns"
    - Cannot exist without a behavior, they must be attached to a behavior.  
	- Can be inherited, they can be overridden by creating the same state/pattern in the new behavior.

## State Group

States have a group, this group can be <code>Neutral</code>, <code>Alert</code>, or <code>Combat</code>.  
For non-NPCs these don't mean anything.  
For NPCs however, they'll belong in that *status* group, for example it'll control their view/hear distance, and the game will force them to be in that NPC state.  
This is a feature re-used from Half-Life 2/Source Engine.

!!! warning "State"
	Every State **must have** a Pattern called <code>pt_default</code>.
	
!!! note "Note"
	All Entities in Postal 3 have an Init State, and Start State,  
	these are usually always called <code>st_init</code> and <code>st_start</code>.

## Patterns

Patterns can be used in two ways, *normally*, or *executed*.  
When *normally* used, the State will enter into that pattern, and will execute code normally.  
When *executed*, the State will **never** enter into that pattern, but **will execute** the pattern's content.

!!! warning "Execute Pattern"
	When executing a pattern, some functions will not work.  
	<code>Wait</code>, <code>Repeat</code> and <code>Pattern</code> will never work, for Pattern you should use <code>State</code> instead.
	
	Like here so:  
	<code>State st_mystate.pt_mypattern</code>

## Naming Convention

!!! tip "Naming Convention"
	TM used a naming convention for Postal3Script, while it's not a must, it is still highly recommended to follow these to avoid confusion in the future:  
	
	- Behaviors always start with <code>bh_</code>
	- States always start with <code>st_</code>
	- Patterns always start with <code>pt_</code>
	- Execute Patterns always start with <code>xpt_</code>

## Inheritance

Postal3Script supports inheritance, states and patterns can be inherited, and they can be overridden when wanted.  
In Postal 3 this is heavily used to split the NPC AI in parts.

Here's an example of inheritance:

```js
// Main core
behavior
{
	name bh_core
	States
	{
		st_corestate
		{
			Group Neutral
			Patterns
			{
				pt_default
				{
					actions
					{
						SetAttr "ea_health 0"
					}
				}
			}
		}
	}
}

// Some behavior
behavior
{
	name bh_myai
	// Inherit from bh_core!
	inherited bh_core
	States
	{
		// Recreate the state to override it!
		st_corestate
		{
			Group Neutral
			Patterns
			{
				pt_default
				{
					actions
					{
						SetAttr "ea_health 100"
					}
				}
				
				xpt_coredefault
				{
					actions
					{
						// Entering our core's state! We'll be absolutely dead.
						State bh_core.st_corestate
					}
				}
			}
		}
	}
}
```

In the example above in <code>bh_core</code> behavior we have a state called <code>st_corestate</code>, when entering it the entity will be dead,
but the entity with the `bh_myai` behavior will not, and instead it will just reset it's health back to 
100.

However, you can still access the core's state by executing <code>xpt_coredefault</code> pattern, this will jump over the overridden state and will just use the core's state instead.

	
### Example of a Behavior with States and Patterns:

```js
behavior
{
	name bh_mybehavior
	States
	{
		st_init
		{
			Group Neutral
			Patterns
			{
				pt_default
				{
					actions
					{
						// Create a timer that fires an event every 2 seconds..
						Timer tLoadCheck,2,repeated
					}
				}
			}
		}
		
		st_start
		{
			Group Neutral
			Patterns
			{
				pt_default
				{
					actions
					{
						SetAttr "loaded 1"
					}
					events
					{
						OnHit				"RemoveAttr loaded"
						OnTimer_tLoadCheck 	"ExecutePattern .xpt_check"
					}
				}
				
				pt_dead
				{
					actions
					{
						// dead, not big surprise
					}
				}
				
				xpt_check
				{
					actions
					{
						// Check if this attribute exist
						CheckAttr "loaded Return 1"
						
						// Well it doesn't exist anymore..
						SetAttr "ea_health 0"
						Timer tLoadCheck,0
						Pattern pt_dead
					}
				}
			}
		}
	}
}
```