<p>Method adds a new office. Office data should be structured in the same format as for <a href="/docs/wsrestv1offices-showupdatedelete-office">updating office</a>.</p>
<h1>
	Parameters</h1>
<p>No additional parameters</p>
<h1>
	Example</h1>
<h2>
	Posted data</h2>
<pre>
<code>
http://ws.idibu.com/ws/rest/v1/offices/new?hash=<your hash>
</code></pre>
<pre>
<code type="xml">
&lt;?xml version=&quot;1.0&quot;?&gt;
&lt;idibu&gt;
    &lt;name&gt;
        new office name
    &lt;/name&gt;
    &lt;contacts&gt;
        &lt;email&gt;test@example.com&lt;/email&gt;
    &lt;/contacts&gt;
&lt;/idibu&gt;
</code></pre>
<h2>
	Response</h2>
<pre>
&lt;code type=&quot;xml&quot;&gt;
&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
    &lt;response&gt;
        &lt;message&gt;Office created&lt;/message&gt;
        &lt;id&gt;33000190&lt;/id&gt;
    &lt;/response&gt;
    &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
