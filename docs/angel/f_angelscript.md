# AngelScript

Executes AngelScript calls.

!!! warning "🪽 Postal III Ultrapatch Angel-only feature"
	This function will only work under Postal III Ultrapatch Angel.
	
## Syntax
`AngelScript "Object:<any> <as_class> <as_function>"` -- Executes AngelScript on the object.  
`AngelScript "Object:<any> <as_class> <as_function> <num_param>"` -- Executes AngelScript on the object, with a number as a parameter.  
`AngelScript "Object:<any> <as_class> <as_function> <text_param>"` -- Executes AngelScript on the object, with a text as a parameter.  
### Global Execution
`AngelScript "GLOBAL <as_class> <as_function>"` -- Executes AngelScript on the object globally.   
`AngelScript "global <as_class> <as_function>"`  
`AngelScript "Global <as_class> <as_function>"`  
`AngelScript "Global <as_class> <as_function> <num_param>"` -- Executes AngelScript on the object globally, with a number as a parameter.  
`AngelScript "Global <as_class> <as_function> <text_param>"` -- Executes AngelScript on the object globally, with a text as a parameter.  

!!! note Note
	`<as_class>` and `<as_function>` must exactly be the same how they were declared in AngelScript.
	**AngelScript is case-sensitive.**

### Example

Globally executed functions will be shared between calls from any object, whereas object-executed functions will store information individually.

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
		
		// Better safe than sorry...
		counter = 0;
	}
	
	int counter;
	
	void Print()
	{
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
	
	void Increment()
	{
		// Increments (adds) it by one
		counter++;
		// Call into MyClass::Print()
		Print();
	}
	
	void Increment_int(int param)
	{
		// Adds to counter from param
		counter += param;
		// Call into MyClass::Print()
		Print();
	}
	
	void Increment_str(string param)
	{
		if (param == "stinky")
		{
			counter += 5;
		}
		else if (param == "deadsaw")
		{
			counter += 10;
		}
		
		// Call into MyClass::Print()
		Print();
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
					// Adds to the counter by 3 for Object:self
					AngelScript "Object:self MyClass Increment_int 3"
					// Adds to the counter by 10 for global
					AngelScript "GLOBAL MyClass Increment_str deadsaw"
				}
			}
		}
	}
}

// Another behavior we are using
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
					// counter will be 12 globally for MyClass
					// (since IN THEORY we already executed it in bh_mybehavior ONCE at some point)
					AngelScript "GLOBAL MyClass Increment"
				}
			}
		}
	}
}
```