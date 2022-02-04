# Hit
<p>Sets weapon proficiency and forces the NPC to attack
<h1>Syntax</h1>
<p><code class="language-js">Hit [float]</code> -- Sets weapon proficiency, and attacks if possible
<pre><code class="language-js">
// from ai_st_init.p3s
Const SPREAD_BLIND,20
Const SPREAD_MAX,10
Const SPREAD_WIDE,6
Const SPREAD_NORMAL,3
Const SPREAD_ACCURACY,1
// from ai_mission_as.p3s
Const SPRD_SNIPE_NERD,5
Const SPRD_NORM_NERD,10
Const SPRD_MOVE_NERD,20
Const SPRD_LEAN_NERD,40
</code></pre>
<h1>Example</h1>
<pre><code class="language-js">
// from ai_mission_jwb.p3s
pt_attack
{
	actions 
	{
		ExecutePattern .xpt_SayFight
		// NPC is a pro at shooting
		Hit 1
		Wait 1
		State st_start
	}
}

// from ai_mission_pdb.p3s
// NPC is seemingly stupid at firing, but when you get closer you'll get punished
pt_attack
{
	actions
	{
		TargetPlayer 1
		
		ExecutePattern .xpt_say
		
		IfAttr "slot#msGP.PlayerNear == 0 Block begin"
			Hit SPREAD_BLIND
			Wait 1:2
		Block end
		
		IfAttr "slot#msGP.PlayerNear == 1 Block begin"
			Hit SPREAD_ACCURACY
			FireEvent Hit
			ChangeAttr "target.ea_health -15"
			Wait 0.5
		Block end
		
		Repeat 0
	}
}
</code></pre>