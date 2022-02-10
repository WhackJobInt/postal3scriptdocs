# Effect

<p>Spawn or interact with a specified particle effect.</p>

<h1>Syntax</h1>
<p><code class="language-js">Effect [slotnum],[effectname],[attachmentpoint],[xpos],[ypos],[zpos],[lifetime],[hitchup]</code> -- Spawns and sets up a particle effect utilizing
all parameters</p>
<p><code class="language-js">Effect [slotnum],[reset]</code> -- Reset an existing particle effect</p>
<p><code class="language-js">Effect [slotnum],[kill]</code> -- Kill an existing particle effect</p>

<p></p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>The <code>slotnum</code> parameter is used to refer to an existing particle effect if needed.</p>
<p>The <code>hitchup</code> parameter makes it parented to the caller, and makes the position offset relative to the specified attachment point.</p>
<p>The <code>attachmentpoint</code> parameter is any bone name of an NPC for example</p>
<p>The names of existing particle effects correspond to their names in their related <code>.pcf</code> file, located in <code>Postal III\p3\particles</code>.
In order to load these particle effects and to view each of the effect names, you will need to load the in-game particle editor in Half-Life 2.
Launch Half-Life 2 with the <code>-tools -nop4</code> launch arguments, and navigate to the particle editor and load one.</p>
<p>Doing <code>reset</code> on a particle effect is basically the same thing as killing it</p>

<p>If you managed to make Hammer++ work somehow, you can view all the particle effects in it's Particle browser.</p>
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
		// (This will make the effect disappear immediately)
		Effect 4,reset

		// Kill the slot 4 particle effect...
		// (This too)
		Effect 4,false
	}
}
</code></pre>