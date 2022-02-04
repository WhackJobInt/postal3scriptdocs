# TargetEntByName
<p>Searches the map for an entity by name, and sets it as the target object if successful.
<h2>Syntax</h2>
<p><code class="language-js">TargetEntByName [string]</code>
<h1>Example</h1>
<pre><code class="language-js">
// (From ai_mission_cw.p3s)
IfAttr "cage_num == 4 Block begin"
	IfAttr "slot#msGP.Cage_04_opened == 0 Repeat 0"
	IfAttr "slot#msGP.Cage_04_opened == 1 Block begin"
		// Search for an entity named "npc_dog_04" from the map
		TargetEntByName npc_dog_04
		IfAttr "Object:target == Object:Null Repeat 0"
		IfAttr "Name:target != String:npc_dog_04 Repeat 0"
		IfAttr "target.Taken == 1 Repeat 0"
		State st_take
	Block end
Block end

// (From "Name" page's Example)
TargetEntByName npc_jen
IfAttr "Name:target == String:npc_jen Block begin"
    // Set jen's health to zero
    SetAttr "target.ea_health 0"
Block end
</code></pre>