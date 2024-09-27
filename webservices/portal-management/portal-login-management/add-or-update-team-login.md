<p>Add/update team login for given portal.</p>
<p>If method is requested by GET request - return information needed to add/update login.</p>
<p>If data is posted to this url using POST or PUT requests - add/update login for portal.</p>
<h1>
	Parameters</h1>
<p>No additional parameters</p>
<h1>
	Requesting subscription information</h1>
<p>To request fields information need to request&nbsp;url&nbsp;with GET method. In response will be returned list of fields needed to be filled in order to add/update user login for portal. Every field has element and type.</p>
<ul>
	<li>
		element - html element for field</li>
	<li>
		type - always login for this request. See&nbsp;<a href="/docs/wsrestv1portalssubscribe-get-subscription-information-specified-portalsubscribe-portal">/ws/rest/v1/portals/&lt;portal ID&gt;/subscribe</a></li>
</ul>
<h1>
	Example</h1>
<h2>
	Request</h2>
<pre>
<code>
GET https://ws.idibu.com/ws/rest/v1/portals/517/set-team-login?hash=<your hash>
</code></pre>
<h2>
	Response</h2>
<pre>
<code type="xml">
<?xml version="1.0" encoding="utf8"?>
<idibu generator="idibu" version="1.0">
    <response>
        <help></help>
        <fields>
            <field>
                <element>text</element>
                <name></name><name>userName</name><title></title>
                <maxchars></maxchars>
                <type>login</type>
            </field>
            <field>
                <element>text</element>
                <name></name><name>userPassword</name><title></title>
                <maxchars></maxchars>
                <type>login</type>
            </field>
        </fields>
    </response>
    <status>success</status>
</idibu>
</code></pre>
<h1 class="p1">
	Add/update team login</h1>
<p class="p2">In order to add/update team login need to post/put variable called <b>data</b> with XML containing filled fields needed to subscribe.</p>
<h1>
	Example</h1>
<h2>
	Posted data</h2>
<pre>
<code>
POST https://ws.idibu.com/ws/rest/v1/portals/517/set-team-login?hash=<your hash>
</code></pre>
<pre>
<code type="xml">
&lt;?xml version=&quot;1.0&quot;?&gt;
&lt;idibu&gt;
    &lt;team-id&gt;33000171&lt;/team-id&gt;
    &lt;fields&gt;
        &lt;field&gt;
            &lt;name&gt;userName&lt;/name&gt;
            &lt;value&gt;user name1&lt;/value&gt;
        &lt;/field&gt;
        &lt;field&gt;
            &lt;name&gt;userPassword&lt;/name&gt;
            &lt;value&gt;user password1&lt;/value&gt;
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
        &lt;message&gt;Team login has been set&lt;/message&gt;
    &lt;/response&gt;
    &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
