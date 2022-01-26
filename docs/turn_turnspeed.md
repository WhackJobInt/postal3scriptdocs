#- Turn
<p>Changes the NPC's angle (from -360 to 360)
<h1>Syntax</h1>
<p><code class="language-js">Turn [integer]</code> -- Increases angle
<p><code class="language-js">Turn -[integer]</code> -- Decreases angle
<p><code class="language-js">Turn [integer]:[integer]</code> -- Randomizes angle
<h1>Example</h1>
<pre><code class="language-js">
// from ai_mission_sbe.p3s
pt_turn_left
{
	actions
	{
		Move false
		SetAttr "CornerType CORNER_RIGHT"
		Turn -90
		Wait 1
		Pattern pt_move
	}
}

pt_turn_right
{
	actions
	{
		Move false
		SetAttr "CornerType CORNER_LEFT"
		Turn 90
		Wait 1
		Pattern pt_move
	}
}
</code></pre>

<br><br><h1>- TurnSpeed</h1>
<p>Sets the NPC's turning speed
<p>The default turning speed is 90
<h1>Syntax</h1>
<p><code class="language-js">TurnSpeed idle, [integer]</code> -- Sets idle speed
<p><code class="language-js">TurnSpeed turn, [integer]</code> -- Sets turn speed
<p><code class="language-js">TurnSpeed walk, [integer]</code> -- Sets walk speed
<p><code class="language-js">TurnSpeed run, [integer]</code> -- Sets run speed
<p><code class="language-js">TurnSpeed attack, [integer]</code> -- Sets attack speed
<p><code class="language-js">TurnSpeed default, [integer]</code> -- Sets default speed
<h1>Example</h1>
<pre><code class="language-js">
// from ai_st1_common.p3s
TurnSpeed turn,15
TurnSpeed idle,15
TurnSpeed run,15					
TurnSpeed walk,15					
TurnSpeed attack,15 
TurnSpeed default,15
</code></pre>