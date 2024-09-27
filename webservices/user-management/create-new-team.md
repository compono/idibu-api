<p>Method adds a new team. Team data should be given to this request in the same format as for <a href="/docs/wsrestv1teams-showupdatedelete-team">updating team</a>.</p>
<p>In the data package, the office-id is mandatory</p>
<h1>
	Parameters</h1>
<p>No additional parameters</p>
<h1>
	Example</h1>
<h2>
	Data posted</h2>
<pre>
<code>
https://ws.idibu.com/ws/rest/v1/teams/new?hash=<your hash>
</code></pre>
<pre>
<code type="xml">
&lt;?xml version=&quot;1.0&quot;?&gt;
&lt;idibu&gt;
    &lt;name&gt;
        my New team
    &lt;/name&gt;
    &lt;office-id&gt;
        33000170
    &lt;/office-id&gt;
&lt;/idibu&gt;
</code></pre>
<h2>
	Response</h2>
<pre>
<code type="xml">
&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
    &lt;response&gt;
        &lt;message&gt;Team created&lt;/message&gt;
        &lt;id&gt;33000172&lt;/id&gt;
    &lt;/response&gt;
    &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
