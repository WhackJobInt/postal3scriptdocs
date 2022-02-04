# ItemType
<p>The type of an item object.
<p>You can find all the item types in a list located in <code>'./Postal III/p3/scripts/ai_matrix.txt'</code>
<h1>Syntax</h1>
<p><code class="language-js">ItemType:[item type]</code> -- Returns the item type specified</p>
<p>Here's the list of all ItemTypes:
<pre><code class="language-js">
item_types
{
	1 TestItem
	2 itmXXX
	3 itmFood
	4 itmToy
	5 itmTrash
	6 itmDrink
	7 itmItem
	8 itmShit
	9 itmCatnip
	10 itmWeapon
	11 itmNasty
	12 Flame
	13 itmSeed
	14 fxTaserBeam
	15 Catnip
	16 Acid
	90 Anchor
}
</code></pre>
<h1>Example</h1>
<pre><code class="language-js">
st_start
{
	group Neutral
	patterns 
	{
		pt_default
		{
			actions
			{
                // If we got a visible entity in our memory slot and it's manner is of ItemType itmShit...
                // Our stupid monkey brain is interested in it, and we want to throw it!
				IfAttr "slot#S_VISIBLE_ENTITY.ea_Manner == ItemType:itmShit	SetAttr want_throw_shit 1"
			}
		}
	}
}
</code></pre>