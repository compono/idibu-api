<p>Method adds a new user. User data should be given to this request in the same format as for <a href="/docs/show-user-profile-settings-and-auth-details-update-profilesettings-remove-user-wsrestv1users">updating user</a>.</p>
<h1>
	Parameters</h1>
<p>No additional parameters</p>
<h1>
	Example</h1>
<h2>
	Data posted</h2>
<pre>
<code>
https://ws.idibu.com/ws/rest/v1/users/new?hash=<your hash>
</code></pre>
<pre>
<code type="xml">
&lt;?xml version=&quot;1.0&quot;?&gt;
&lt;idibu&gt;
    &lt;profile&gt;
            &lt;firstname&gt;John&lt;/firstname&gt;
            &lt;lastname&gt;Doe&lt;/lastname&gt;
            &lt;company&gt;Company&lt;/company&gt;
            &lt;contacts&gt;&lt;address&gt;Far away 1234&lt;/address&gt;
               &lt;address-line1&gt;Far away&lt;/address-line1&gt;
               &lt;address-line2&gt;&lt;/address-line2&gt;
               &lt;address-line3&gt;&lt;/address-line3&gt;
               &lt;country&gt;Far away&lt;/country&gt;
               &lt;postcode&gt;7777&lt;/postcode&gt;
               &lt;email&gt;tescior@tescior.pl&lt;/email&gt;
               &lt;phone&gt;+777 0 777 77777&lt;/phone&gt;
               &lt;fax&gt;&lt;/fax&gt;
               &lt;www&gt;www.page.com&lt;/www&gt;
            &lt;/contacts&gt;
    &lt;/profile&gt;
    &lt;auth&gt;
        &lt;disabled&gt;No&lt;/disabled&gt;
        &lt;login&gt;newuser4&lt;/login&gt;
        &lt;password&gt;somepwd4&lt;/password&gt;
    &lt;/auth&gt;
&lt;/idibu&gt;
</code></pre>
<h2>
	Response</h2>
<pre>
<code type="xml">
&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
    &lt;response&gt;
        &lt;message&gt;User added&lt;/message&gt;
        &lt;id&gt;1198&lt;/id&gt;
    &lt;/response&gt;
    &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>

Max length for username and password fields is 32 characters. Anything beyond that will be trimmed.
