<p>Method shows/edits/removes team</p>
<ul>
	<li>GET - view team information/settings</li>
	<li>POST - edit team settings</li>
	<li>DELETE - remove team</li>
</ul>
<h1>Parameters</h1>
<p>No additional parameters</p>
<h1>Getting team information</h1>
<p>Returns selected team's data (team 7654321 in the example).</p>
<h2>Example</h2>
<h3>Request</h3>
<pre><code>https://ws.idibu.com/ws/rest/v1/teams/7654321?hash=YOUR_HASH</code></pre>
<h3>Response</h3>
<pre><code type="xml">&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
	&lt;response&gt;
		&lt;id&gt;7654321&lt;/id&gt;
		&lt;name&gt;Test team&lt;/name&gt;
		&lt;office-id&gt;1234567&lt;/office-id&gt;
		&lt;contacts&gt;
			&lt;need-authorization&gt;No&lt;/need-authorization&gt;
		&lt;/contacts&gt;
	&lt;/response&gt;
	&lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
<h1>Updating team information</h1>
<p>To update team information, pass an xml in the <code>data</code> parameter. Any field or block can be omitted - pass only the fields which need updating (team 7654321 in the example).</p>
<h2>Example</h2>
<h3>Posted data</h3>
<pre><code>POST https://ws.idibu.com/ws/rest/v1/teams/7654321?hash=YOUR_HASH</code></pre>
<pre><code type="xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot;?&gt;
&lt;idibu&gt;
	&lt;name&gt;Test team&lt;/name&gt;
	&lt;contacts&gt;
		&lt;need-authorization&gt;No&lt;/need-authorization&gt;
	&lt;/contacts&gt;
&lt;/idibu&gt;
</code></pre>
<h3>Response</h3>
<pre><code type="xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
	&lt;response&gt;
		&lt;message&gt;Team updated&lt;/message&gt;
	&lt;/response&gt;
	&lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
<h1>Deleting a team</h1>
<p>To delete a team, use a DELETE request (team 7654321 in the example).</p>
<h2>Example</h2>
<h3>Data posted</h3>
<pre><code>DELETE https://ws.idibu.com/ws/rest/v1/teams/7654321?hash=YOUR_HASH</code></pre>
<h3>Response</h3>
<pre><code type="xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
    &lt;response&gt;
        &lt;message&gt;Team deleted&lt;/message&gt;
    &lt;/response&gt;
    &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
