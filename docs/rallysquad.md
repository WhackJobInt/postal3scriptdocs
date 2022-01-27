# RallySquad
<p>Unused Postal3Script function
<h2>Technical Details</h2>
<p>* Searches for nearest NPC with a squad, If both squads exist, removes the first member of NPC's squad, and adds it to nearest NPC's squad
<p>* If NPC's squad exists, nearest NPC will be added to NPC's squad
<p>* If NPC's squad doesn't exists, the opposite will happen
<p>* If both NPCs don't have any squads, a squad will be automatically created with both NPCs being the members of it
<h2>Syntax</h2>
<p><code class="language-js">RallySquad [distance], [squad size]</code>