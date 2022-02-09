# Effect

<p>Spawn or interact with a specified particle effect.</p>

<h1>Syntax</h1>
<p><code class="language-js">Effect [slotnum],[effectname],[attachmentpoint],[xpos],[ypos],[zpos],[lifetime],[hitchup]</code> -- Spawns and sets up a particle effect</p>

<p></p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>The <code>slotnum</code> parameter is used to refer to an existing particle effect if needed.</p>
<p>The <code>hitchup</code> parameter makes it parented to the caller, and makes the position offset relative to the specified attachment point.</p>
<p>The names of existing particle effects correspond to their names in their related <code>.pcf</code> file, located in <code>Postal III\p3\particles</code>.
In order to load these particle effects and to view each of the effect names, you will need to load the in-game particle editor and you will need Half-Life 2 installed. 
Launch Half-Life 2 with the <code>-tools -nop4</code> launch arguments, and navigate to the particle editor and load them yourself.</p>
</div>

<h1>Example</h1>
<pre><code class="language-js">
pt_default
{
	actions
	{
		// Spawn a Tazer_Hit_Smoke_Fx particle effect assigned to slot 4, attached to the pelvis, 
		// with a z position offset, infinite lifetime, and hitched up to to us...
		Effect 4,Tazer_Hit_Smoke_Fx,pelvis,0,0,-12,-1,true

		// Reset the slot 4 particle effect...
		Effect 4,reset

		// Kill the slot 4 particle effect...
		Effect 4,false
	}
}
</code></pre>