# Attributes

In Postal3Script you are able to set or check Attributes, and execute states according to the results.

All attributes in Postal3Script are integers only.

When checking against multiple attributes at once you can use the "and" keyword.

## IfAttr

Checks if an Attribute or Object has met a condition. 
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>The Attribute or Object MUST be set using the <code>SetAttr</code> function first, or already exist.</p>
</div>

<pre><code class="language-js">
st_IfAttrTutorial
{
	Group Neutral
	Patterns
	{
		pt_default
		{
			actions
			{
				// Check for my faction, if it's Zealots then I love animals
				IfAttr "ea_faction == Faction:Zealots SetAttr LoveAnimals 1"
				
				// My target is the player, so I will hate them
				IfAttr "Object:target == Object:player SetAttr HatesPlayer 1"
				
				// I have no ranged weapon, but I do have a melee weapon, then I'll bring up my weapon
				IfAttr "HasWeapon:Ranged == 0 and HasWeapon:melee > 0 Block begin"
					IfAttr "HasWeapon:melee != 2 SetAttr WeaponChanged 1"
					Weapon select,melee
					SetAttr "ea_status sPUNISHER"
				Block end
				
				// Player is forgiven according to the timer
				IfAttr "Timer:tForgivePlayer <= 0 Pattern pt_end"
				
				// State didn't execute from the Player, returning from this point
				IfAttr "Object:caller != Object:player Return 1"
				
				// My target loves animals?? No way!
				IfAttr "target.LoveAnimals == 1 Return 1"
				
				// My enemy of my enemy... is my enemy now!
				IfAttr "target.Object:target != Object:null Block begin"
					AssistTarget 1
				Block end
				
				// My target is the Player, and they have their python out
				IfAttr "Object:target == Object:player and target.ea_games == 1 State so_seepiss"
			}
		}
	}
}
</code></pre>

## SetAttr

Creates and sets a new attribute value if it doesn't exist, or just sets it if it already exists.

<pre><code class="language-js">
Constants
{
	Const YES,1
	Const NO,0
}

st_SetAttrTutorial
{
	Group Neutral
	Patterns
	{
		pt_default
		{
			actions
			{
				SetAttr "IamTheDevil 666"
				
				// Supports constants
				SetAttr "y_Yes YES"
				SetAttr "n_No NO"
				SetAttr "ea_status sNEUTRAL"
				SetAttr "reaction RE_NONE"
				
				// Randomize non-existent attributes
				// Maximum possible is 100
				// Second value should always be zero
				SetAttr "rnd 0,0,100"
				SetAttr "rndtwo 25,0,75"
				
				// Sets other object's attribute
				SetAttr "target.cr_demo YES"
				SetAttr "caller.cr_demo NO"
			}
		}
	}
}
</code></pre>

## CheckAttr

Checks if an Attribute is true (equal to 1).

<pre><code class="language-js">
st_CheckAttrTutorial
{
	Group Neutral
	Patterns
	{
		pt_default
		{
			actions
			{
				CheckAttr "flag_static Return 1"
				CheckAttr "greet_sleazy Say SLEEZ"
				CheckAttr "AnimalNotCat Say LIKESANIMAL"
				CheckAttr "AnimalCat Say LIKESANIMAL,LIKESCAT"
			}
		}
	}
}
</code></pre>

## ChangeAttr

Changes an already existing Attribute's value, increasing, decreasing, multiplying, or by halving.

<ul>
<div class="admonition warning">
<p class="admonition-title">Warning</p>
ChangeAttr has some several flaws that are good to keep in mind:</p>
<li>It MUST have an operator, simply having a number inside the parameter without an operator will NOT touch the attribute!</li>
<p>
<li>Only capable of working with values up to 100.</li>
<p>
<li>If value will exceed 100, it will reset back to 0.</li>
<p>
<li>Halving will round the value upwards ('5 / 2' would be '3').</li>
</div>
</ul>

<pre><code class="language-js">
st_ChangeAttrTutorial
{
	Group Neutral
	Patterns
	{
		pt_default
		{
			actions
			{
				// Randomization
				ChangeAttr "poo_rnd 0:100"
				ChangeAttr "combat_rnd 0:1"
				
				ChangeAttr "DonutsIHave +1"
				ChangeAttr "PooIGive -1"
				ChangeAttr "Multiply *5"
				ChangeAttr "Halve /5"
				
				// Change Health on the fly
				ChangeAttr "ea_health +25"
				
				// Set this Attribute to absolute zero
				ChangeAttr "MyAttribute -MyAttribute"
			}
		}
	}
}
</code></pre>

## RemoveAttr

Removes an already existing Attribute. Cannot be accessed and isn't set anymore.

<pre><code class="language-js">
st_RemoveAttrTutorial
{
	Group Neutral
	Patterns
	{
		pt_default
		{
			actions
			{
				RemoveAttr "flag_PlayerFriendly"
				RemoveAttr "poo_rnd"
				RemoveAttr "IamTheDevil"
			}
		}
	}
}
</code></pre>