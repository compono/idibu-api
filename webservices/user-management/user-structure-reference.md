<p>Method returns the list of users in office/team|Unassigned structure</p>
<p>It can also show you the list of users that a user can post on behalf or authorise job for. To do that please user the following parameters:<br><br>
postable-by=[USER ID]<br>
authorized-by=[USER ID]<br>
<br>
<h1>
	Example</h1>
<h2>
	Request</h2>
<pre>
<code>
http://ws.idibu.com/ws/rest/v1/users/structure?hash=<your hash>
</code></pre>
<h2>
	Response</h2>
<pre>
<code type="xml">
&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
    &lt;response&gt;
        &lt;unassigned&gt;
            &lt;user email=&quot;uu1@idibu.com&quot; id=&quot;167&quot; name=&quot;Unassigned user 1&quot;&gt;
            &lt;user email=&quot;uu2@idibu.com&quot; id=&quot;193&quot; name=&quot;Unassigned user 2&quot;&gt;
        &lt;/user&gt;&lt;/user&gt;&lt;/unassigned&gt;
        &lt;offices&gt;
            &lt;office id=&quot;35000009&quot; name=&quot;Office1&quot;&gt;
                &lt;team id=&quot;35000010&quot; name=&quot;Team1&quot;&gt;
                &lt;user email=&quot;u1@idibu.com&quot; id=&quot;147&quot; name=&quot;Team1 user&quot;&gt;
                &lt;user email=&quot;u2@idibu.com&quot; id=&quot;141&quot; name=&quot;Team1 user2&quot;&gt;
                &lt;/user&gt;&lt;/user&gt;&lt;/team&gt;
            &lt;/office&gt;
        &lt;/offices&gt;
    &lt;/response&gt;
    &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
