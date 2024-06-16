# AngelScript

Executes AngelScript calls.

!!! warning "🪽 Postal 3 Angel-only feature"
	This function will only work under Postal 3 Angel.
	
## Syntax
`AngelScript "Object:<any> <as_class> <as_function>"` -- Executes AngelScript on the object.  
`AngelScript "GLOBAL <as_class> <as_function>"`  
`AngelScript "global <as_class> <as_function>"`  
`AngelScript "Global <as_class> <as_function>"` -- Executes AngelScript on the object globally.   

### Example

Globally executed functions will be shared between calls from any object, whereas object executed functions will store information individually.

!!! note Note  
	If this is still confusing, there's a more detailed tutorial available on the [AngelScript docs](https://whackjobint.github.io/angelscript/tutorials/gettingstarted/).

```
// Rough example of an AngelScript class
// (not stored in a P3S file)
class MyClass : IPostal3Script
{
	CP3SObj@ self;
	MyClass(CP3SObj@ obj)
	{
		// If we are attempting to use it as Global 
		// then we must check if obj exist..
		if (@obj != null)
			@self = obj;
		
		counter = 0;
	}
	
	int counter;
	
	void Increment()
	{
		counter++;
		Printf("MyClass::Increment %d ", counter);
		
		if (@self == null)
		{
			Printf("(GLOBAL)\n");
		}
		else
		{
			Printf("(%s|%s)\n", self.GetManner(), self.GetFaction());
		}
	}
}

// Rough example of a P3S behavior
// (stored in P3S)
behavior
{
	name bh_mybehavior
	States
	{
		// This state is being called, or executed somewhere else
		st_mystate
		{
			Group Neutral
			Patterns
			{
				pt_default
				{
					// counter will be 1 for Object:self
					AngelScript "Object:self MyClass Increment"
					// counter will be 1 globally for MyClass
					AngelScript "GLOBAL MyClass Increment"
				}
			}
		}
	}
}

// Another behavior we are using
// Just for the sake of this example I'm trying to make this as less confusing as possible
behavior
{
	name bh_myotherbehavior
	States
	{
		// This state is being called, or executed somewhere else
		st_mystate
		{
			Group Neutral
			Patterns
			{
				pt_default
				{
					// counter will be 1 for Object:self
					AngelScript "Object:self MyClass Increment"
					// counter will be 2 globally for MyClass
					// (since IN THEORY we already executed it in bh_mybehavior once at some point)
					AngelScript "GLOBAL MyClass Increment"
				}
			}
		}
	}
}
```