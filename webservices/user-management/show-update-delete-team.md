<p>Method shows/edits/removes team</p>
<ul>
	<li>
		GET - view team information/settings</li>
	<li>
		POST - edit team settings</li>
	<li>
		DELETE - remove team</li>
</ul>
<h1>
	Parameters</h1>
<p>No additional parameters</p>
<h1>
	Getting team information</h1>
<p>Return team information</p>
<h2>
	Example</h2>
<h3>
	Request</h3>
<pre>
<code>
http://ws.idibu.com/ws/rest/v1/teams/33000171?hash=<your hash>
</code></pre>
<h3>
	Response</h3>
<pre>
<code type="xml">
&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
    &lt;response&gt;
        &lt;id&gt;33000171&lt;/id&gt;
        &lt;name&gt;tiraspol&lt;/name&gt;
        &lt;office-id&gt;33000170&lt;/office-id&gt;
    &lt;/response&gt;
    &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
<h1>
	Updating team information</h1>
<p>To update team information need to pass xml of the same format as in response to the GET request in data parameter. Any field or block can be omited, pass in the xml only those fields which you need update.</p>
<h2>
	Example</h2>
<h3>
	Posted data</h3>
<pre>
<code>
POST http://ws.idibu.com/ws/rest/v1/teams/33000171?hash=<your hash>
</code></pre>
<pre>
<code type="xml">
<?xml version="1.0"?>
<idibu>
    <name>
        new team name
    </name>
</idibu>
</code></pre>
<h3>
	Response</h3>
<pre>
<code type="xml">
&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
    &lt;response&gt;
        &lt;message&gt;Team updated&lt;/message&gt;
    &lt;/response&gt;
    &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
<h1>
	Deleting team</h1>
<p>To delete a team you need to use the DELETE request</p>
<h2>
	Example</h2>
<h3>
	Data posted</h3>
<pre>
<code>
DELETE http://ws.idibu.com/ws/rest/v1/teams/33000171?hash=<your hash>
</code></pre>
<h3>
	Response</h3>
<pre>
<code type="xml">
&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
    &lt;response&gt;
        &lt;message&gt;Team deleted&lt;/message&gt;
    &lt;/response&gt;
    &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
