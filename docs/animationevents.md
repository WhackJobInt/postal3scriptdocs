# Animation Events
<p>Character models' animation files have embedded/scripted events in them, which call P3S events.</p>
<p>Unlike every other engine attributes or events, these ones can be edited by decompiling animation files.</p>

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>- Animation Events will always be called on the host.</p>
<p>- Animation Events are animation frame specific.</p>
<p>- The syntax for calling a P3S event on a frame is <code>{ event AE_P3_SCRIPTED_ANIM_EVENT 33 "EVENTNAMEGOESHERE" }</code></p>
<p>- Above syntax would be calling <code>OnAnimEVENTNAMEGOESHERE</code> P3S event on frame <code>33</code></p>
<p>- Not all models/animations have script events</p>
</div>

<div class="admonition warning">
<p class="admonition-title">Warning</p>
<p>- Human models do not share animations, they have individual animation files, if you edit one, you MUST edit the rest of them to be consistent!</p>
<p>- Due to Postal 3 having a different MDL format, it's not possible to decompile animation files and then recompile them back again, you will have to use a custom MDL file to create new or override animations.</p>
</div>


<br>

## Cat (cat.mdl/cat_animations.mdl)
<code>Sequence/Gesture name</code> -- <code>P3S event it will call</code>
<pre><code class="language-js">
idle_take 	-- OnAnimTAKE
</code></pre>
<br>


## Dog (champ.mdl/champ_animations.mdl)
<code>Sequence/Gesture name</code> -- <code>P3S event it will call</code>
<pre><code class="language-js">
idle_poo 		-- OnAnimPOO
idle_take 		-- OnAnimTAKE
idle_give		-- OnAnimGIVE
idle_bark_1		-- OnAnimBARK
idle_eat_out	-- OnAnimYUMMY
</code></pre>
<br>

## Rhino (rhino.mdl)
<code>Sequence/Gesture name</code> -- <code>P3S event it will call</code>
<div class="admonition warning">
<p class="admonition-title">Warning</p>
<p>Rhino calls multiple P3S events in one sequence!</p>
</div>
<pre><code class="language-js">
Run_Gallop 		-- OnAnimRhinoStompFR
				-- OnAnimRhinoStompBR
				-- OnAnimRhinoStompBL
				-- OnAnimRhinoStompFL
</code></pre>
<br>

## All Human Models
<code>Sequence/Gesture name</code> -- <code>P3S event it will call</code>
<div class="admonition warning">
<p class="admonition-title">Warning</p>
<p>Some scripted events are missing from certain NPCs (i.e. KrotchyNPC), the events below are extracted from M_Avg and F_Avg anims (which are copy pasted onto other NPC models)!</p>
</div>
<pre><code class="language-js">
dialogue_no		-- OnAnimHEY
env_lifting		-- OnAnimTAKE
env_discard		-- OnAnimDROP
env_throw		-- OnAnimTHROW
env_phone_in	-- OnAnimTAKE
env_phone_out	-- OnAnimDROP
melee_attack2	-- OnAnimHIT
melee_attack3	-- OnAnimHIT
melee_attack4	-- OnAnimPUSH_MEDIUM
melee_attack5	-- OnAnimHIT
melee_attack6	-- OnAnimHIT
melee_attack7	-- OnAnimHIT
melee_push2		-- OnAnimPUSH_HEAVY
melee_box_01_L	-- OnAnimHIT (Male models only)
melee_box_01_R	-- OnAnimHIT (Male models only)
melee_box_02_L	-- OnAnimHIT (Male models only)
melee_box_02_R	-- OnAnimHIT (Male models only)
melee_box_03	-- OnAnimHIT (Male models only)
melee_push		-- OnAnimPUSH_HEAVY
melee_push_easy	-- OnAnimPUSH_EASY
melee_kick1		-- OnAnimPUSH_HEAVY
melee_kick2		-- OnAnimKICK
zombie_barf		-- OnAnimBARF
g_idle_Drinking	-- OnAnimYUM (Male models only)
g_idle_Feeding	-- OnAnimYUM (Male models only)
</code></pre>
<br>