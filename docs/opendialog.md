# OpenDialog
<p>Opens the Yes/No dialog
<p>Unused/Unfinished Postal3Script function
<h1>Technical Details</h1>
<p>Executes "gameui_show_p3_yes_no_dialog" console command with parameters
<pre><code class="language-js">
// The console command will ignore any parameter
OpenDialog 0
</code></pre>
<h1>Events followed by Answer</h1>
<p>Depending on the answer, it will fire the event called "OnDialogNo" or "OnDialogYes" for the Actor that executed it.
<p>Normally it would mean the executed Actor would be the Player, but in this function there's no hardcoded check for the Player.