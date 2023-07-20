## SetBehavior

<p>Sets an entity's behavior/AI on the fly.</p>

<div class="admonition warning">
<p class="admonition-title">Catharsis Reborn Feature</p>
<p>The following function will only work in <b>Catharsis Reborn</b>.</p>
</div>

<h1>Syntax</h1>
<p><code>SetBehavior [behavior]</code> -- Sets only the behavior.</p>
<p><code>SetBehavior [behavior],[init_state]</code> -- Sets the behavior and init state only.</p>
<p><code>SetBehavior [behavior],[init_state],[start_state]</code> -- Sets behavior, init, and start state only.</p>
<p><code>SetBehavior [behavior],[init_state],[start_state],[faction]</code> -- Sets behavior, init, start state, and the faction only.</p>
<p><code>SetBehavior [behavior],[init_state],[start_state],[faction],[manner]</code> -- Sets everything for this entity.</p>

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Will use 'st_init' and 'st_start' for init and start states if there weren't any defined.</p>
<p><b>Faction</b> and <b>Manner</b> will be reused from current AI if it was never defined.</p>
<p>Will create 'setbehavior_lock' attribute to prevent spamming as it can crash the game. Set it to zero if you wish to set the AI once again.</p>
</div>

<h1>Example</h1>
<pre><code class="language-js">
// This will make any NPC to use a Cat's AI/behavior
pt_meow
{
	actions
	{
		SetAttr "setbehavior_lock 0"
		SetBehavior bh_cat,st_init,st_start,Animals,PussyCat
		Wait 3
		State st_start
	}
}

// This will make the NPC to just only switch a behavior
pt_betterAI
{
	actions
	{
		SetAttr "setbehavior_lock 0"
		SetBehavior bh_npc_hulk
		Wait 3
		State st_start
	}
}

// This will make the Dog switch behavior and start with an unique init state
pt_friendly
{
	actions
	{
		SetAttr "setbehavior_lock 0"
		SetBehavior bh_dog,st_init_friendly
		Wait 3
		State st_start
	}
}
</code></pre>