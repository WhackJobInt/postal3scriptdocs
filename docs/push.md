# Push
<p>Makes an NPC perform a shove/push melee attack.
<h1>Syntax</h1>
<p><code class="language-js">Push self, target, easy</code> -- Plays flinching animations, but no damage
<p><code class="language-js">Push self, target, medium</code> -- Deals slight damage to target
<p><code class="language-js">Push self, target, hard</code> -- Deals heavy damage to target
<p>Victim and attacker cannot be the same.
<h1>Example</h1>
<pre><code class="language-js">
// From ai_citizen.p3s
// Plays animation and deals damage at the same time
pt_bump
{
	actions
	{
		TargetCaller 1
		TargetToMem msTARGET
		IfAttr "ea_Manner == Manner:RedNeck and slot#msTARGET.ea_Manner == StreetBro Block begin"
			Face true
			Sequence seq.melee_push
			Push self,target,medium
		Block end
		IfAttr "ea_Manner == Manner:StreetBro and slot#msTARGET.ea_Manner == StreetBro Block begin"
			Face true
			Sequence seq.melee_push
			Push self,target,medium
		Block end
		IfAttr "ea_Manner == Manner:CuteGirl and slot#msTARGET.ea_Manner == StreetBro Block begin"
			Face true
			Sequence seq.melee_push
			Push self,target,medium
		Block end
		State st_start
	}
}
</code></pre>