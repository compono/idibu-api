<p>Method sets user/team/office quotas in batch.<br/>
	<code>quota</code> is the amount of quotas.<br/>
	<code>limit</code> is the amount to which the quotas reset after the specified period (see <a href="https://github.com/oneworldmarket/idibu-api/blob/master/webservices/quota-management/add-quota-to-portal.md" target="_blank">add-quota-to-portal<a/>).</p>
<h1>Example</h1>
<h2>Data posted</h2>
<pre><code>POST https://ws.idibu.com/ws/rest/v1/quotas/517/all?hash=YOUR_HASH</code></pre>
<pre>
<code type="xml">&lt;?xml version=&quot;1.0&quot;?&gt;
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
</code></pre>
<h2>Response</h2>
<pre>
<code type="xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
    &lt;response&gt;
        &lt;message&gt;At least one quota should be set&lt;/message&gt;
    &lt;/response&gt;
    &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
