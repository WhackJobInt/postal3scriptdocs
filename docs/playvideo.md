# PlayVideo
<p>Plays a .bik movie from "Postal III/p3/media" folder
<h1>Syntax</h1>
<p><code class="language-js">PlayVideo 'filename', 'fade_in_time', 'fade_out_time', 'console_command(s) to execute after Video finished playing'</code>
<h1>Technical Details</h1>
<p>Will execute "p3_playvideo" or "p3_playvideo_exitcommand" console commands
<p>Syntax for "p3_playvideo_exitcommand" is 'filename', 'exitcommand', 'fadein', 'fadeout'
<p>Syntax for "p3_playvideo" is 'filename', 'fadein', 'fadeout'
<h1>Example</h1>
<pre><code class="language-js">
// Fades in and fades out in 1.5 seconds
PlayVideo placeholder, 1.5, 1.5

// Fades in and fades out in 1 second
PlayVideo thebigrevenge, 1, 1

// Alternative (requires pcc entity in the level)
EntFireInput "pcc,Command:playvideo thebigrevenge"

// Another alternative
// Will play music, and text after video had ended
EntFireInput "pcc,Command:playgamesound Music.IntroStinger"
EntFireInput "pcc,Command:video_exitcmd notimportant gameui_show_p3_briefdlg #CR_MONDAY_BRIEFING"
</code></pre>
<h1>Issues</h1>
<p>* Depending on which command will you use for video playing, it will become unskippable.
<p>* Postal3Script is too slow to play an intro movie on the beginning of a map, causing it you to see the map for a brief second before eventually playing the movie.