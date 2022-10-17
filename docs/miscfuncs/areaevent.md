# AreaEvent

<p>Fires event on nearby P3S entities, with filtering.</p>

<h1>Syntax</h1>
<p><code class="language-js">AreaEvent [eventname],[radius],[filter1],[filter2],[filter3],...</code> -- Fires area event</p>

<p></p>
<div class="admonition note">
<p class="admonition-title">Note</p>
<p>Filtering can be <code>Manner</code>, <code>Faction</code>, and <code>State</code> name.</p>
<p><code>[radius]</code> is always multiplied by 32.</p>
<p>Events will be called OnAE_<code>[eventname]</code>.</p>
<p>Multiple filters work via ANY execution, this means the function will execute the event on entities that meet ANY of the criteria!</p>
</div>

<h1>Example</h1>
<pre><code class="language-js">
// This state is called when an NPC dies, let's do something else with it...
st_corpse
{
	Group Alert
	Patterns
	{
		pt_default:ignore_ext_events
		{
			actions
			{
				// This will only execute for the Player,
				// since it's Manner and Faction is always "Player"
				AreaEvent "YouDie,2,Player"
				
				// This however will only execute if an NPC's state is currently st_idle
				AreaEvent "ScaryCorpse,3,st_idle"
				
				// If you want to limit it to cops instead...
				// The event will only be fired if they are in st_idle state, and their Faction
				// is called Police
				AreaEvent "CopScaryCorpse,3,st_idle,Police"
				
				// Let's repeat it.. so events will get fired over and over again
				Wait 3
				Repeat 0
			}
		}
	}
}

// We assume this is an NPC behavior's st_idle state, pay attention to the events!
// Note: don't copy this as is, as it won't work, but it's an example how it should work
st_idle
{
	Group Neutral
	Patterns
	{
		...
	}
}
events
{
	// Note: these events can be Global if you want, since AreaEvent will only get fired if
	// they are in st_idle state anyway!
	OnAE_ScaryCorpse 	"State st_fear"
	OnAE_CopScaryCorpse "State st_investigate"
}
</code></pre>