# Memory Functions

## TargetToMem

Takes target object, and puts it into a memory slot

<h1>Syntax</h1>
<p><code class="language-js">TargetToMem [slot]</code> -- Places target object to [slot] slot</p>
<h1>Example</h1>
<pre><code class="language-js">
// (Code taken from ai_cashmart_npc.p3s and edited it)
// This will save this entity to the third memory slot, and resets it's target
TargetEntByName target_1floor_zealots
TargetToMem 3
ResetTarget 1
</code></pre>

<br>
## TargetFromMem

Takes an object from a memory slot, and sets it as target

<h1>Syntax</h1>
<p><code class="language-js">TargetFromMem [slot]</code> -- Takes object from [slot] slot</p>
<h1>Example</h1>
<pre><code class="language-js">
// (Continuing from TargetToMem's Example)
// This forces the target to be an enemy after taking it out from memory
TargetFromMem 3
Relationship target, enemy, 1
ResetTarget 1
</code></pre>

<br>
## CallerToMem

Takes caller object, and places it into a memory slot (an Event was fired and had a valid caller object)

<h1>Syntax</h1>
<p><code class="language-js">CallerToMem [slot]</code> -- Places caller object to [slot] slot</p>

<br>
## ClearMem

Clears a memory slot

<h1>Syntax</h1>
<p><code class="language-js">ClearMem [slot]</code> -- Clears an object from [slot] slot</p>