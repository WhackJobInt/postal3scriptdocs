# Porn World (ai_mission_pw.p3s)
<h1>Pre-Path</h1>

You not only have to clean up someone's *wank*, but you also have to defend the store from being destroyed.  
No one pays the Postal Dude high enough for this.

<p>Porn World does not have unused behaviors in it's script file.
<p>All used behavior names in the level:
<pre><code class="language-js">
'bh_drocher'
'bh_pw_logic'
'bh_mom'
'bh_strip_girl'
'bh_ron'
'bh_punisher' -- Cop
'bh_mom_shooter'
</code></pre>
<p>'bh_ron' has a commented out pattern called 'pt_spawnDrocha' which would have spawned a tissue in his right hand and drop it.
<p>'bh_drocher' has a commented out pattern called 'pt_sayHereEmployed!'
<pre><code class="language-js">
// from 'bh_ron'
pt_spawnDrocha
{
    SpawnItem drocha_spwn,owner,hand_right
    Item drop
}

// from 'bh_drocher'
pt_sayHereEmployed!
{
    actions 
	{
        TargetCaller 1
        IfAttr "checkCount < 4 and DistTo:target < 5 and Visible:target == 1 Block begin"
            ChangeAttr "checkCount 1"
            Pattern pt_default
        Block end
        Face true
        Sequence "seq.confusion_active"
        WaitForEnd 1
        Face false
        Timer "sayBusy,0"
        SetHintGroup wish_fun_idle
        Pattern pt_end
	}
}
</code></pre>