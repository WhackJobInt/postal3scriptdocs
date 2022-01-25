# PlayerKarma
<p>Sets the Player's karma globally
<h1>Syntax</h1>
<pre><code class="language-js">
(from ai_st_init.p3s)

// KARMA AMOUNTS
Const KARMA_LOW,5
Const KARMA_MED,10
Const KARMA_HIGH,25
Const KARMA_HALF,50
Const KARMA_FULL,100
</code></pre>
<p><code class="language-js">PlayerKarma hide</code> -- Hides the karma icon
<p><code class="language-js">PlayerKarma show</code> -- Shows the karma icon
<p><code class="language-js">PlayerKarma good</code> -- Player is now on good path
<p><code class="language-js">PlayerKarma evil</code> -- Player is now on evil path
<p><code class="language-js">PlayerKarma +-*/='value'</code> -- Modifies the karma value
<p>'good' and 'evil' is completely unused
<h1>Example</h1>
<pre><code class="language-js">
// from ai_mission_sbe.p3s
xpt_OnPaparazziEscaped
{
	actions
	{
		SetAttr "PhotoTaken 1"
		MissionLog fail,photos
		
		// Player lost some good guy points
		CheckAttr "PhotoTaken PlayerKarma -KARMA_HIGH"
	}
}
</code></pre>