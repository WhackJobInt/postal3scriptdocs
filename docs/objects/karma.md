# Karma
<p>Unused Postal3Script Object</p>
<p>Sets or gets the Player's karma.</p>

<div class="admonition warning">
<p class="admonition-title">Warning</p>
<p>It's recommended to use <a href="../../missionfuncs/playerkarma">PlayerKarma</a> instead.</p>
</div>

<h1>Example</h1>
<pre><code class="language-js">
// (from ai_st6_missions.p3s)
SetAttr "karma_delta player.karma"
ChangeAttr "karma_delta -karma_cur"
SetAttr "karma_cur player.karma"
</code></pre>