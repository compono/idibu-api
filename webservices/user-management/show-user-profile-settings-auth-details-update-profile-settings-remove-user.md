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
<p><b>Note:</b> For editing administrative account details you can use `admin` instead of numeric user id, like: https://ws.idibu.com/ws/rest/v1/users/admin?hash=&lt;your hash&gt; . You can also use admin logins for that: <your hash=""></your>https://ws.idibu.com/ws/rest/v1/users/admin?user=&lt;username&gt;&amp;password=&lt;password&gt;</p>
<h1>
	Example</h1>
<h2>
	Request</h2>
<pre>
<code>
https://ws.idibu.com/ws/rest/v1/users/485?hash=<your hash>
</code></pre>
<h2>
	Response</h2>
	
```xml

<?xml version="1.0" encoding="utf8"?>
<idibu generator="idibu" version="1.0">
    <response>
        <profile>
            <id>485</id>
            <title></title>
            <firstname>vit</firstname>
            <lastname>Dyatlov</lastname>
            <company>Idibu</company>
            <team-id>33000183</team-id>
            <contacts>
                <address>Tiraspol, Moldova 3357</address>
                <address-line1>Tiraspol</address-line1>
                <address-line2></address-line2>
                <address-line3></address-line3>
                <country>Moldova</country>
                <postcode>3357</postcode>
                <email>vitaly@idibu.com</email>
                <phone>+373 0 777 15818</phone>
                <fax></fax>
                <www>idibu.com</www>
            </contacts>
        </profile>
        <settings>
            <alerts>
                <job-expiry>Off</job-expiry>
                <new-applicant>Off</new-applicant>
            </alerts>
            <apsearch>
                <enable>Yes</enable>
                <results>email</results>
                <step1>Yes</step1>
            </apsearch>
            <access-report>No</access-report>
        </settings>
        <auth>
            <disabled>No</disabled>
            <login>myPrivatelogin</login>
            <password>somep4ssword</password>
        </auth>
    </response>
    <status>success</status>
</idibu>
```

<h1>
	Updating user information</h1>
<p>To update user information need to pass xml of the same format as in response to the GET request in data parameter. Any field or block can be omited, pass in the xml only those fields which you need update. You can send both login and password fields empty to remove the user's login.</p>
<h2>
	Example</h2>
<h3>
	Data posted</h3>
<pre>
<code>
POST https://ws.idibu.com/ws/rest/v1/users/485?hash=<your hash>
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
<p>&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
&lt;response&gt;
&lt;message&gt;User updated&lt;/message&gt;
&lt;/response&gt;
&lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;</p>
<h1>
	Deleting user</h1>
<p>To delete user you need to use a DELETE request</p>
<h1>
	Example</h1>
<h2>
	Request</h2>
<pre>
<code>
DELETE https://ws.idibu.com/ws/rest/v1/users/485?hash=<your hash>
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
