# Gesture/Sequence Functions

## Gesture

Make an NPC perform a gesture

<h2>Syntax</h2>
<p><code class="language-js">Gesture [gesture_name]</code> -- Play gesture by name</p>
<p><code class="language-js">Gesture [gesture_name,duration]</code> -- Play gesture with duration</p>
<p><code class="language-js">Gesture [gesture_name,duration:bias]</code> -- Play gesture with optional duration and bias</p>

<div class="admonition note">
<p class="admonition-title">Note</p>
<p><code>bias</code> is the max amount of time that is randomly generated and tacked onto the gesture duration!
</p>
</div>

<h2>Example</h2>
<pre><code class="language-js">
Gesture g_onfire // Do on fire gesture forever, until reset
Gesture g_emote_afraid,2:2 // Do afraid gesture with duration of 2 seconds and a bias of 2
Gesture g_onfire,3 // Do on fire gesture for 3 seconds
</code></pre>

<br>
## ResetGesture

Reset an NPC's gesture(s)

<div class="admonition warning">
<p class="admonition-title">TODO</p>
<p>Make sure that <code>ResetGesture 1</code> actually does reset the current gesture!
</p>
</div>

<h2>Syntax</h2>
<p><code class="language-js">ResetGesture [gesture_name]</code> -- Reset specific gesture by name</p>
<p><code class="language-js">ResetGesture 1</code> -- Reset current gesture</p>
<p><code class="language-js">ResetGesture all</code> -- Reset ALL gestures</p>
<p><code class="language-js">ResetGesture *</code> -- Reset ALL gestures</p>

<pre><code class="language-js">
ResetGesture g_onfire // Reset specific gesture by name
ResetGesture 1 // Reset current gesture
ResetGesture all // Reset ALL gestures
ResetGesture * // Reset ALL gestures
</code></pre>

<br>
## ResetSequence

Reset an NPC's sequence

<div class="admonition warning">
<p class="admonition-title">TODO</p>
<p>Make sure that <code>ResetGesture 1</code> actually does reset the current sequence!
</p>
</div>

<h2>Syntax</h2>
<p><code class="language-js">ResetGesture 1</code> -- Reset current sequence
<pre><code class="language-js">
ResetGesture 1 // Reset current sequence
</code></pre>