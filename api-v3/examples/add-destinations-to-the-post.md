<p>Even if only a few of the possible posting destinations were sent in the original XML request, it is possible to let the user add more destinations to the page. By changing the following config value in the request:</p>
<pre>
<code>
&lt;!-- ... --&gt;
&nbsp;&lt;method&gt;ADD&lt;/method&gt;
&nbsp;&lt;config&gt;
&nbsp;&nbsp;&lt;show_durations&gt;No&lt;/show_durations&gt;
&nbsp;&nbsp;&lt;lockboards&gt;No&lt;/lockboards&gt;
&nbsp;&nbsp;&lt;partnerid&gt;yourpartnerid&lt;/partnerid&gt;
&lt;!-- ... --&gt;
</code></pre>
<p>The system will return a PCP, even if no errors were found as you have said you explicitly want to be able to choose posting destinations:</p>
<pre>
<code>
&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot; ?&gt;
&lt;idibu&gt;
&nbsp;&lt;job status=&quot;delayed&quot; id=&quot;31003375&quot; postingid=&quot;342&quot;&gt;
&nbsp;&nbsp;&lt;postcompletionurl&gt;http://pascal-adpost.idibu.com/cBzfG.html&lt;/postcompletionurl&gt;
&nbsp;&lt;/job&gt;
&lt;/idibu&gt;
</code></pre>
