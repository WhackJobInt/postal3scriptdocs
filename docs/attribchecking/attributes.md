# Attributes

In Postal3Script you are able to set or check Attributes, and execute states according to the results.

All attributes in Postal3Script are integers only.

When checking against multiple attributes at once you can use the <code>AND</code> keyword.

## IfAttr

Checks if an Attribute or Object has met a condition. 
<div class="admonition warning">
<p class="admonition-title">Bugs</p>
<p>The Attribute or Object <b>MUST</b> be set using the <code>SetAttr</code> function first, or already exist.</p>
<p>If it doesn't exist, IfAttr will <b>NOT</b> work properly, so keep this in mind!</p>
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

<p>Creates and sets a new attribute value if it doesn't exist, or just sets it if it already exists.</p>
<p>Third and fourth parameter is for setting a minimum and maximum value for <code>ChangeAttr</code></p>
<p>If <b>no parameters are given</b>, the minimum and maximum value of the attribute <b>will always be</b> 0 and 100</p>
<p>A minimum and maximum value can be set like this:</p>
<code>SetAttr "myattribute [initial value],[minimum],[maximum]"</code>

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
				
				// Set an attribute with minimum and maximum values
				// this should be 0 for min, and 100 for max
				SetAttr "rnd 0,0,100"
				// this should be 5 for min and 75 for max
				SetAttr "rndtwo 25,5,75"
				// this will execute events for ChangeAttr (although it works without on_change_event)
				SetAttr "myattribute 5,0,100,on_change_event"
				
				// Sets other object's attribute
				SetAttr "target.cr_demo YES"
				SetAttr "caller.cr_demo NO"
			}
		}
	}
}
</code></pre>

## CheckAttr

Checks if an Attribute exists or not. Works with <code>Ammo</code> type.

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
				
				SetAttr "exists 0"
				CheckAttr "myattrib Block begin"
					SetAttr "exists 1"
				Block end
				
				IfAttr "exists == 1 Block begin"
					Pattern pt_somepattern
				Block end
				
				SetAttr "I_have_ammo 0"
				CheckAttr "Ammo:self SetAttr I_have_ammo 1"
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
ChangeAttr has some several flaws that must be kept in mind:</p>
<li>It MUST have an operator, simply having a number inside the parameter without an operator will NOT touch the attribute!</li>
<p>
<li>Will ONLY work within the attribute's minimum and maximum values.</li>
<p>
<li>If value will exceed the attribute's maximum value, it will reset back to it's minimum value.</li>
<p>
<li>Halving will round the value upwards ('5 / 2' would be '3').</li>
<p>
<li>Attribute <b>MUST</b> exist when you try to modify it! It has the same flaws like IfAttr.</li>
<br>
<p>A minimum and maximum value can be set via SetAttr:</p>
<li>SetAttr "myattribute [initial value],[minimum],[maximum]"</li>
</div>
</ul>

<ul>
<div class="admonition note">
<p class="admonition-title">Note</p>
Creates or executes the following events:</p>
<li>OnAttrMin_[attribute] -- executes when Attribute reaches it's set minimum value</li>
<p>
<li>OnAttrMax_[attribute] -- executes when Attribute reaches it's set maximum value</li>
<p>
<li>OnAttrChange_[attribute] -- executes whenever Attribute's value changes</li>
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
	events
	{
		OnAttrMin_PooIGive		"State st_createmorepoo"
		OnAttrMax_DonutsIHave	"State st_eatdonuts"
		OnAttrChange_ea_health	"EmitSound munchmunch"
	}
}
</code></pre>

## RemoveAttr

Removes an already existing Attribute. Cannot be accessed and isn't set anymore.

<ul>
<div class="admonition note">
<p class="admonition-title">Note</p>
Creates or executes the following event:</p>
<li>OnAttrRemove_[attribute] -- executes when Attribute was removed</li>
</div>
</ul>

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
	events
	{
		OnAttrRemove_IamTheDevil	"EmitSound darthvader_noooooo"
	}
}
</code></pre>