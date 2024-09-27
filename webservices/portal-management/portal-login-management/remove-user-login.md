<p>Method removes user login from specified portal</p>
<h1>
	Parameters</h1>
<p>No additional parameters</p>
<h1>
	Example</h1>
<h2>
	Request</h2>
<pre>
<code>
DELETE https://ws.idibu.com/ws/rest/v1/portals/123/remove-user-login?user-id=234&hash=<your hash>
</code></pre>
<h2>
	Response</h2>
<pre>
<code type="xml">
&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
    &lt;response&gt;
        &lt;message&gt;User login has been removed&lt;/message&gt;
    &lt;/response&gt;
    &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
