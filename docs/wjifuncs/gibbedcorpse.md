## GibbedCorpse

<p>Slices a Human entity into gibs.</p>

<div class="admonition warning">
<p class="admonition-title">Catharsis Reborn Feature</p>
<p>The following function will only work in <b>Catharsis Reborn</b>.</p>
</div>

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>This function is recommended to use if you wish to use corpses for decoration purposes, but still want to use Corpse AI and stimuli.</p>
</div>

<h1>Params</h1>
```
1 	-- GC_HEAD
2 	-- GC_LEGS
3 	-- GC_ARMS
4 	-- GC_LEFTLEG 			// 5 -- GC_RIGHTLEG
6 	-- GC_LEFTARM 			// 7 -- GC_RIGHTARM
8 	-- GC_TORSO
9 	-- GC_LOWERBODY 		// 10 -- GC_UPPERBODY
11 	-- GC_EVERYTHING 		(param1 only)
12 	-- GC_HEAD_LEGS_ARMS 	(param1 only)
```

<h1>Syntax</h1>
`GibbedCorpse <param1>,<param2>,<param3>`
```{ .lang linenos=true }
GibbedCorpse 1 			// NPC only has a head
GibbedCorpse 4 			// NPC only has a leg
GibbedCorpse 2 			// NPC only has both legs
GibbedCorpse 6 			// NPC only has an arm
GibbedCorpse 3 			// NPC only has both arms
GibbedCorpse 8,9,10 	// NPC only has torso, head, arms
GibbedCorpse 12			// NPC only has head, legs, and arms (separately)
GibbedCorpse 1,8,9		// NPC only has head, and torso
GibbedCorpse 11			// NPC is completely sliced up
```