<p>Method returns quota settings for specified portal</p>
<h1>
	Parameters</h1>
<p>No additional parameters</p>
<h1>
	Example</h1>
<h2>
	Request</h2>
<pre>
<code>
http://ws.idibu.com/ws/rest/v1/quotas/517?hash=<your hash>
</code></pre>
<h2>
	Response</h2>
<pre>
<code type="xml">
&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
    &lt;response&gt;
        &lt;type&gt;period&lt;/type&gt;
        &lt;period&gt;Year&lt;/period&gt;&lt;base /&gt;Post
        &lt;month-renewal&gt;01&lt;/month-renewal&gt;
        &lt;year-renewal&gt;22-11&lt;/year-renewal&gt;
        &lt;reset&gt;Ignore&lt;/reset&gt;
    &lt;/response&gt;
    &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
