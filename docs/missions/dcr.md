# Diseased Cat Roundup (ai_mission_dcr.p3s)
<h1>Pre-Path</h1>

Infinite hostile NPC generator, they are also very annoying.  
Did I also mention how this mission is so hard because you have to catch so many cats?

<p>Below you will only see the behavior names, and a rough guessing from the code on what they were supposed to do.
<p>Unused behavior name(s) from script file:
<pre><code class="language-js">
'bh_dcr_civil_static' -- Sets static flag (flag_static)
</code></pre>
<p>All behavior names used in the level:
<pre><code class="language-js">
'bh_dog'
'bh_cop_hub1'
'bh_cellphone'
'bh_dcr_cat' -- is in script file
'bh_cats_mission' -- is in script file
'bh_sushi' -- is in script file
'bh_shit'
'bh_dcr_civil' -- is in script file
'bh_dcr_sewer_hobo' -- is in script file
'bh_dcr_street_hobo' -- is in script file
'bh_dcr_civil_house' -- is in script file
'bh_dcr_civil_shopper' -- is in script file
'bh_dcr_civil_shopkeeper' -- is in script file
'bh_trash'
</code></pre>
<pre><code class="language-js">
// the unused behavior
behavior
{
	name bh_dcr_civil_static
	inherited bh_dcr_civil
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
						SetAttr "flag_static 1"
						ExecutePattern bh_base:st_init.pt_default
					}
				}
			}
		}
	}
}
</code></pre>