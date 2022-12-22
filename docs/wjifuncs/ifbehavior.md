## IfBehavior

<p>Checks if an entity's behavior is equal to this condition.</p>

<div class="admonition warning">
<p class="admonition-title">Catharsis Reborn Feature</p>
<p>The following function will only work in <b>Catharsis Reborn</b>.</p>
</div>

<h1>Syntax</h1>
```{ .lang linenos=true }
IfBehavior "<behavior to check against> Block begin"
	// do stuff
Block end
```

<h1>Example</h1>
```{ .lang linenos=true }
// Assuming this is in the parent behavior of bh_dog and bh_cat (bh_animal)
xpt_checkanimal
{
	actions
	{
		IfBehavior "bh_dog Block begin"
			State st_dog
		Block end
		
		IfBehavior "bh_cat Block begin"
			State st_cat
		Block end
	}
}
```