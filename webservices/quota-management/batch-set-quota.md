<p>Method sets user/team/office quotas in batch</p>
<h1>
	Example</h1>
<h2>
	Data posted</h2>
<pre>
<code>
POST http://ws.idibu.com/ws/rest/v1/quotas/517/all?hash=<your hash>
</code></pre>
<pre>
<code type="xml">
&lt;?xml version=&quot;1.0&quot;?&gt;
&lt;idibu&gt;
&lt;quotas&gt;
    &lt;quota&gt;
        &lt;user-id&gt;138&lt;/user-id&gt;
        &lt;quota&gt;42&lt;/quota&gt;
        &lt;limit&gt;88&lt;/limit&gt;
    &lt;/quota&gt;
    &lt;quota&gt;
        &lt;team-id&gt;35000010&lt;/team-id&gt;
        &lt;quota&gt;42&lt;/quota&gt;
        &lt;limit&gt;88&lt;/limit&gt;
    &lt;/quota&gt;
    &lt;quota&gt;
        &lt;office-id&gt;35000009&lt;/office-id&gt;
        &lt;quota&gt;42&lt;/quota&gt;
        &lt;limit&gt;88&lt;/limit&gt;
    &lt;/quota&gt;
&lt;/quotas&gt;
&lt;/idibu&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;h2&gt;
	Response&lt;/h2&gt;
&lt;pre&gt;
&lt;code type=&quot;xml&quot;&gt;
&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
    &lt;response&gt;
        &lt;message&gt;At least one quota should be set&lt;/message&gt;
    &lt;/response&gt;
    &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
