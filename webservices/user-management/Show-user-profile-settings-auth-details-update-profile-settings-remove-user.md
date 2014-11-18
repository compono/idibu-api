<p>Method shows/edits/removes user</p>
<ul>
	<li>
		GET - view user information/settings</li>
	<li>
		POST - edit user settings</li>
	<li>
		DELETE - remove user</li>
</ul>
<h1>
	Parameters</h1>
<p>No additional parameters</p>
<h1>
	Getting user information</h1>
<p>Return user information, settings and auth credentials.</p>
<p><b>Note:</b> For editing administrative account details you can use `admin` instead of numeric user id, like: http://ws.idibu.com/ws/rest/v1/users/admin?hash=&lt;your hash&gt; . You can also use admin logins for that: <your hash=""></your>http://ws.idibu.com/ws/rest/v1/users/admin?user=&lt;username&gt;&amp;password=&lt;password&gt;</p>
<h1>
	Example</h1>
<h2>
	Request</h2>
<pre>
<code>
http://ws.idibu.com/ws/rest/v1/users/485?hash=<your hash>
</code></pre>
<h2>
	Response</h2>
<pre>
<code type="xml">
&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
    &lt;response&gt;
        &lt;profile&gt;
            &lt;id&gt;485&lt;/id&gt;&lt;title&gt;&lt;/title&gt;
            &lt;firstname&gt;vit&lt;/firstname&gt;
            &lt;lastname&gt;Dyatlov&lt;/lastname&gt;
            &lt;company&gt;Idibu&lt;/company&gt;
            &lt;team-id&gt;33000183&lt;/team-id&gt;
            &lt;contacts&gt;&lt;address&gt;Tiraspol, Moldova 3357&lt;/address&gt;
                &lt;address-line1&gt;Tiraspol&lt;/address-line1&gt;
                &lt;address-line2&gt;&lt;/address-line2&gt;
                &lt;address-line3&gt;&lt;/address-line3&gt;
                &lt;country&gt;Moldova&lt;/country&gt;
                &lt;postcode&gt;3357&lt;/postcode&gt;
                &lt;email&gt;vitaly@idibu.com&lt;/email&gt;
                &lt;phone&gt;+373 0 777 15818&lt;/phone&gt;
                &lt;fax&gt;&lt;/fax&gt;
                &lt;www&gt;idibu.com&lt;/www&gt;
            &lt;/contacts&gt;
        &lt;/profile&gt;
        &lt;settings&gt;
            &lt;alerts&gt;
                &lt;job-expiry&gt;Off&lt;/job-expiry&gt;
                &lt;new-applicant&gt;Off&lt;/new-applicant&gt;
            &lt;/alerts&gt;
            &lt;apsearch&gt;
                &lt;enable&gt;Yes&lt;/enable&gt;
                &lt;results&gt;email&lt;/results&gt;
                &lt;step1&gt;Yes&lt;/step1&gt;
            &lt;/apsearch&gt;
            &lt;access-report&gt;No&lt;/access-report&gt;
        &lt;/settings&gt;
        &lt;auth&gt;
            &lt;disabled&gt;No&lt;/disabled&gt;
            &lt;login&gt;myPrivatelogin&lt;/login&gt;
            &lt;password&gt;somep4ssword&lt;/password&gt;
        &lt;/auth&gt;
    &lt;/response&gt;
    &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
<h1>
	Updating user information</h1>
<p>To update user information need to pass xml of the same format as in response to the GET request in data parameter. Any field or block can be omited, pass in the xml only those fields which you need update.</p>
<h2>
	Example</h2>
<h3>
	Data posted</h3>
<pre>
<code>
POST http://ws.idibu.com/ws/rest/v1/users/485?hash=<your hash>
</code></pre>
<pre>
<code type="xml">
&lt;?xml version=&quot;1.0&quot;?&gt;
&lt;idibu&gt;
    &lt;profile&gt;
        &lt;firstname&gt;updated-user&lt;/firstname&gt;
    &lt;/profile&gt;
    &lt;auth&gt;
        &lt;login&gt;vitaly&lt;/login&gt;
    &lt;/auth&gt;
&lt;/idibu&gt;
</code></pre>
<h3>
	Response</h3>
<?xml version="1.0" encoding="utf8"?>
<p><idibu generator="idibu" version="1.0"> <response> <message>User updated</message> </response> <status>success</status> </idibu></p>
<h1>
	Deleting user</h1>
<p>To delete user you need to use a DELETE request</p>
<h1>
	Example</h1>
<h2>
	Request</h2>
<pre>
<code>
DELETE http://ws.idibu.com/ws/rest/v1/users/485?hash=<your hash>
</code></pre>
<h2>
	Response</h2>
<pre>
<code type="xml">
&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
    &lt;response&gt;
        &lt;message&gt;User has been deleted&lt;/message&gt;
    &lt;/response&gt;
    &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
