<p>Method used to set tracking parameters when using when using application URL method applying </p>

</h1>Example of getting settings</h1>
<h2>
	Request</h2>
<pre>
<code>
http://ws.idibu.com/ws/rest/v1/tracking?hash=<your hash>
</code></pre>
<h2>
	Response</h2>
<pre>
<code type="xml">
&lt;parameters&gt;
  &lt;board&gt;board-parameter&lt;/board&gt;
  &lt;job&gt;job-parameter&lt;/job&gt;
&lt;/parameters&gt;
</code></pre>


<p>	You can also check the tracking parameters set</p>
<h2>
	Request</h2>
<pre>
<code>
GET http://ws.idibu.com/ws/rest/v1/tracking?hash=?hash=<your hash>
</code>
