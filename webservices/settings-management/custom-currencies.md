<p>Method to list custom currencies for specific clients based on the hash id</p>
<h1>
	list of currencies idibu can support</h1>
<pre>
<code>http://ws.idibu.com/ws/rest/v1/currencies?hash=<hash></code></pre>
<pre>
<code type="xml">
&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
&lt;response&gt;
    &lt;currencies&gt;
        &lt;currency&gt;
            &lt;id&gt;AED&lt;/id&gt;
            &lt;name&gt;UAE Dirham &lt;/name&gt;
        &lt;/currency&gt;
            (...)
    &lt;/currencies&gt;
&lt;/response&gt;
&lt;/idibu&gt;</code>
</pre>
<p>At the moment those currencies can be only set by idibu&#39;s staff on support@idibu.com; Once requested currencies are enabled, they can be listed using the following:</p>
<pre>
<code>http://ws.idibu.com/ws/rest/v1/currencies/available?hash=<hash></code></pre>
