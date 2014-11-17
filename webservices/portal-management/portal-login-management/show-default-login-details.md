<p>Method returns default login information</p>
<h1>
	Parameters</h1>
<p>No additional parameters</p>
<h1>
	Example</h1>
<h2>
	Request</h2>
<pre>
<code>
http://ws.idibu.com/ws/rest/v1/portals/123/default-login?hash=<your hash>
</code></pre>
<h2>
	Response</h2>
<pre>
&lt;code type=&quot;xml&quot;&gt;
&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
    &lt;response&gt;
        &lt;fields&gt;
            &lt;field&gt;
                &lt;name&gt;userName&lt;/name&gt;
                &lt;value&gt;test1&lt;/value&gt;
            &lt;/field&gt;
            &lt;field&gt;
                &lt;name&gt;userPassword&lt;/name&gt;
                &lt;value&gt;test1&lt;/value&gt;
            &lt;/field&gt;
        &lt;/fields&gt;
    &lt;/response&gt;
    &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
