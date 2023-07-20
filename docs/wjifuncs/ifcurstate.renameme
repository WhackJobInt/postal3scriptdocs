## IfCurState

<p>Checks if entity is in a specified State.</p>

<div class="admonition warning">
<p class="admonition-title">Catharsis Reborn Feature</p>
<p>The following function will only work in <b>Catharsis Reborn</b>.</p>
</div>

<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Can only work with <code>Block begin</code> and <code>Block end</code>.</p>
</div>

<h1>Syntax</h1>
<p><pre>
<code>
IfCurState "[state to check] Block begin"
// do stuff
Block end
</code>
</pre>

<h1>Example</h1>
<pre>
<code>
// Checks if the entity is in st_idle state
xpt_checkidle
{
	actions
	{
		IfCurState "st_idle Block begin"
			SetAttr "idling 1"
			Return 1
		Block end
		
		SetAttr "idling 0"
	}
}
</code>
</pre>