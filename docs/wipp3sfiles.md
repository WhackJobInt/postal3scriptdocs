# Unused Postal3Script files
These files can be found in <code>(location of P3)/p3/scripts/</code>

Many of them contain cut and planned features for the open world gameplay, ultimately they were never ported over properly.

It's a good idea to search through these files for hunting for Beta content that never made it out alive.

They were used by the scripters to test and develop scripts before eventually moving them over to mission scripts.

They were also used to test many P3S functions to ensure they are working properly.

<pre><code class="language-js">
'ai_badger_test.p3s' - Badger testing
'ai_cashmart.p3s' - Earlier version of Cashmart (ai_cashmart_npc.p3s is not unused)
'ai_gameplay.p3s' - Intended for Open World gameplay
'ai_patrol1_citizen_fight.p3s' - Unknown
'ai_st1_common.p3s' - Contains various old code
'ai_st2_states.p3s' - Contains various old code
'ai_st3_social.p3s' - Contains experimental old code
'ai_st4_queuie.p3s' - Queue testing
'ai_st5_temp.p3s' - Contains test code, scrapped features
'ai_st6_missions.p3s' - Test code related to missions
'ai_st7_environment.p3s' - Code related to cut environment behavior
'ai_st8_items.p3s' - Code related to cut inventory items
'ai_st9_animals.p3s' - Animals test
'ai_st10_temp.p3s' - Test script, contains code related to Traffic lights
'ai_st11_urza.p3s' - Contains scrapped features, old code
'ai_st12_urza.p3s' - Contains scrapped features, old code
'ai_st98_helicopter.p3s' - Code that is identical to the Helicopter AI that IS used
'ai_st_utilities.p3s' - Various code related to NPCs
'ai_test_babuska.p3s' - Test script
'lean_test.p3s' - Test script
</code></pre>

!!! warning "Warning"

    Don't try loading them as is, they have a very outdated Postal3Script layout, and several deleted functions!  
    Use <code>p3_fsm_spew 1</code> console command to check which one of them loads properly!