<p>Add/update user login for given portal.</p>
<p>If method is requested by GET request - return information needed to add/update login.</p>
<p>If data is posted to this url using POST or PUT requests - add/update login for portal.</p>
<h1>
	Parameters</h1>
<p>No additional parameters</p>
<h1>
	Requesting subscription information</h1>
<p>To request fields information need to request url with GET method. In response will be returned list of fields needed to be filled in order to add/update user login for portal. Every field has element and type.</p>
<ul>
	<li>
		element - html element for field</li>
	<li>
		type - always login for this request. See <a href="/docs/wsrestv1portalssubscribe-get-subscription-information-specified-portalsubscribe-portal">/ws/rest/v1/portals/&lt;portal ID&gt;/subscribe</a></li>
</ul>
<h1>
	Example</h1>
<h2>
	Request</h2>
<pre>
<code>
GET http://ws.idibu.com/ws/rest/v1/portals/517/set-user-login?hash=<your hash>
</code></pre>
<h2>
	Response</h2>
<pre>
<code type="xml">
&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
    &lt;response&gt;
        &lt;help&gt;&lt;/help&gt;
        &lt;fields&gt;
            &lt;field&gt;
                &lt;element&gt;text&lt;/element&gt;
                &lt;name&gt;userName&lt;/name&gt;&lt;title&gt;&lt;/title&gt;
                &lt;maxchars&gt;&lt;/maxchars&gt;
                &lt;type&gt;login&lt;/type&gt;
            &lt;/field&gt;
            &lt;field&gt;
                &lt;element&gt;text&lt;/element&gt;
                &lt;name&gt;userPassword&lt;/name&gt;&lt;title&gt;&lt;/title&gt;
                &lt;maxchars&gt;&lt;/maxchars&gt;
                &lt;type&gt;login&lt;/type&gt;
            &lt;/field&gt;
        &lt;/fields&gt;
    &lt;/response&gt;
    &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
<h1>
	Add/update user login</h1>
<p>In order to add/update user login need to post/put variable called <strong>data</strong> with XML containing filled fields needed to subscribe.</p>
<h1>
	Example</h1>
<h2>
	Posted data</h2>
<pre>
<code>
POST http://ws.idibu.com/ws/rest/v1/portals/517/set-user-login?hash=<your hash>
</code></pre>
<pre>
<code type="xml">
<?xml version="1.0"?>
&lt;idibu&gt;
    &lt;user-id&gt;682&lt;/user-id&gt;
    &lt;fields&gt;
        &lt;field&gt;
            &lt;name&gt;userName&lt;/name&gt;
            &lt;value&gt;put your user name here&lt;/value&gt;
        &lt;/field&gt;
        &lt;field&gt;
            &lt;name&gt;userPassword&lt;/name&gt;
            &lt;value&gt;put your password here&lt;/value&gt;
        &lt;/field&gt;
    &lt;/fields&gt;
&lt;/idibu&gt;
</code></pre>
<h2>
	Response</h2>
<pre>
<code type="xml">
&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
    &lt;response&gt;
        &lt;message&gt;User login has been set&lt;/message&gt;
    &lt;/response&gt;
    &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
