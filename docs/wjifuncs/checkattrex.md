## CheckAttrEx

<p>Extended/Alternative version of CheckAttr.</p>

<div class="admonition warning">
<p class="admonition-title">Catharsis Reborn Feature</p>
<p>The following function will only work in <b>Catharsis Reborn</b>.</p>
</div>

<h1>Syntax</h1>
`CheckAttrEx "<target object> Home:<target2 object> <action>"` -- Checks if `<target object>` has the Home flag (normally this would mean they are a home intruder).</p>
`CheckAttrEx "<target object> <attribute> <action>"` -- Checks if `<target object>` has `<attribute>`.</p>

<h1>Example</h1>
```
// Example code of trespassing
xpt_OnVisible
{
	actions
	{
		TargetCaller 1
		
		IfAttr "RelationTo:target == Relation:enemy State st_start"
		IfAttr "RelationTo:target == Relation:fear  State st_start"
		
		CheckAttrEx "Object:caller Home:self Block begin"
			Timer tTrespassBlob,15
			Headblob 5,HomeTrespass
			ExecutePattern st_idle.xpt_Trespasser
			Return 1
		Block end
		
		...
	}
}
```