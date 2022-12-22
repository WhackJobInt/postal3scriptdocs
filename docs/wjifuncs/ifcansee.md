## IfCanSee

<p>Conditional function which checks if pointer can be seen by the entity.</p>

<div class="admonition warning">
<p class="admonition-title">Catharsis Reborn Feature</p>
<p>The following function will only work in <b>Catharsis Reborn</b>.</p>
</div>

<h1>Syntax</h1>
<pre><code class="language-js">
// Checks if it blocks line of sight
IfCanSee "[target/caller/player] Block begin"
	// stub
Block end

// Checks if it blocks line of sight AND if it faces the target
IfCanSee "[target:view/caller:view/player:view] Block begin"
	// stub
Block end
</code></pre>

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>This function doesn't support one line execution. It must have <b>Block begin</b> and <b>Block end</b>.</p>
<p>TODO: this should get fixed at some point</p>
</div>

<h1>Example</h1>
<pre><code class="language-js">
// This will check if Player is visible regardless if it's facing it, and goes to a different pattern
pt_playercheck
{
	actions
	{
		TargetPlayer 1
		IfCanSee "target Block begin"
			Pattern pt_playersee
		Block end
		
		Pattern pt_playercheckagain
	}
}

// This check will only pass if the entity is facing the player and there's nothing that blocks it's line of sight
pt_playerlos
{
	actions
	{
		TargetPlayer 1
		IfCanSee "target:view Block begin"
			Pattern pt_attack
		Block end
		
		Pattern pt_end
	}
}
</code></pre>