# Animation Events
Character models' animation files have embedded/scripted events in them, which call P3S events.

Unlike every other engine attributes or events, these ones can be edited by decompiling animation files.

!!! note "Note"

    - Animation Events will always be called on the host.<br><br>
    - Animation Events are animation frame specific.<br><br>
    - The syntax for calling a P3S event on a frame is: 
	    - <code>{ event AE_P3_SCRIPTED_ANIM_EVENT 33 "EVENTNAMEGOESHERE" }</code>
        - This would call <code>OnAnimEVENTNAMEGOESHERE</code> P3S event on frame <code>33</code><br><br>
	
    - Not all models/animations have script events

!!! warning "Warning"

    - Human models **do not share** animations, they have individual animation files, if you edit one, you **MUST** edit the rest of them to be consistent!<br><br>
    - Due to Postal 3 having a different MDL format, it's not possible to decompile animation files and then recompile them back again, you will have to use a custom MDL file to create new or override animations.

## Cat (cat.mdl/cat_animations.mdl)

| Sequence/Gesture Name | Postal3Script Event |
|-----------------------|---------------------|
| idle_take				| OnAnimTake		  |

<br>

## Dog (champ.mdl/champ_animations.mdl)

| Sequence/Gesture Name | Postal3Script Event |
|-----------------------|---------------------|
| idle_poo				| OnAnimPOO		 	  |
| idle_take				| OnAnimTAKE		  |
| idle_give				| OnAnimGIVE		  |
| idle_bark_1			| OnAnimBARK		  |
| idle_eat_out			| OnAnimYUMMY		  |

<br>

## Rhino (rhino.mdl)

!!! warning "Warning"

    Rhino calls multiple P3S events in one sequence!

| Sequence/Gesture Name | Postal3Script Event |
|-----------------------|---------------------|
| Run_Gallop			| OnAnimRhinoStompFR  |
| Run_Gallop  			| OnAnimRhinoStompBR  |
| Run_Gallop			| OnAnimRhinoStompBL  |
| Run_Gallop			| OnAnimRhinoStompFL  |

<br>

## All Human Models

!!! warning "Warning"

    Some scripted events are missing from certain NPCs (i.e. KrotchyNPC), the events below are extracted from M_Avg and F_Avg anims (which are copy pasted onto other NPC models)!

| Sequence/Gesture Name | Postal3Script Event 		|
|-----------------------|---------------------------|
|dialogue_no			| OnAnimHEY                 |
|env_lifting			| OnAnimTAKE                |
|env_discard			| OnAnimDROP                |
|env_throw				| OnAnimTHROW               |
|env_phone_in			| OnAnimTAKE                |
|env_phone_out			| OnAnimDROP                |
|melee_attack2			| OnAnimHIT                 |
|melee_attack3			| OnAnimHIT                 |
|melee_attack4			| OnAnimPUSH_MEDIUM         |
|melee_attack5			| OnAnimHIT                 |
|melee_attack6			| OnAnimHIT                 |
|melee_attack7			| OnAnimHIT                 |
|melee_push2			| OnAnimPUSH_HEAVY          |
|melee_box_01_L			| OnAnimHIT *(Male only)*   |
|melee_box_01_R			| OnAnimHIT *(Male only)*   |
|melee_box_02_L			| OnAnimHIT *(Male only)*   |
|melee_box_02_R			| OnAnimHIT *(Male only)*   |
|melee_box_03			| OnAnimHIT *(Male only)*   |
|melee_push				| OnAnimPUSH_HEAVY          |
|melee_push_easy		| OnAnimPUSH_EASY           |
|melee_kick1			| OnAnimPUSH_HEAVY          |
|melee_kick2			| OnAnimKICK                |
|zombie_barf			| OnAnimBARF                |
|g_idle_Drinking		| OnAnimYUM *(Male only)*   |
|g_idle_Feeding			| OnAnimYUM *(Male only)*   |

<br>