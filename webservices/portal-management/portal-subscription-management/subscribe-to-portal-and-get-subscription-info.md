<p>If you make a GET request to this URL, providing that the portal ID is valid, and you provide as well your hash, the system will return the subscription information for that board; namely, the list of fields that are required to subscribe to the board, the type of the field, and the possible values if applies. You will have to provide tags for non-required fields, but feel free to leave them blank if you don&#39;t wish to provide any value.</p>
<p>&nbsp;</p>
<p>In order to subscribe, you have to make a POST request to the same address, with the `data` parameter set to the XML that provides the subscription information.</p>
<p>&nbsp;</p>
<p>You can find examples of the information returned by the system when making either kind of request, and how the data should be sent when subscribing to a portal.</p>
<h1>
	Parameters</h1>
<p>No additional parameters</p>
<h1>
	Requesting subscription information</h1>
<p>To request subscription information need to request url with GET method. In response will be returned list of fields needed to be filled in order to subscribe to portal. Every field has element and type.</p>
<ul>
	<li>
		element - html element for field</li>
	<li>
		type - can be general or login.
		<ul>
			<li>
				general - field is used globally for portal.</li>
			<li>
				login - field is used to create logins for offices/teams/users, when subscribing to portal fields of login type are used to set global default login.</li>
		</ul>
	</li>
</ul>
<h1>
	Example</h1>
<h2>
	Request</h2>
<pre>
<code>
GET http://ws.idibu.com/ws/rest/v1/portals/123/subscribe?hash=<your hash>
</code></pre>
<h2>
	Response</h2>
<pre>
<code type="xml">
&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
    &lt;response&gt;
        &lt;help&gt;Please contact the board before your first posting and let them know you\&amp;#39;ll be using idibu as your service provider. They need to enable proper option on their end first.&lt;/help&gt;
        &lt;fields&gt;
            &lt;field&gt;
                &lt;element&gt;select&lt;/element&gt;
                &lt;name&gt;stv_method&lt;/name&gt;
                &lt;values&gt;
                    &lt;value&gt;
                        &lt;name&gt;Please Select...&lt;/name&gt;
                        &lt;value&gt;&lt;/value&gt;
                    &lt;/value&gt;
                    &lt;value&gt;
                        &lt;name&gt;Auto Forwarded Applications&lt;/name&gt;
                        &lt;value&gt;AutoForwardedApplications&lt;/value&gt;
                    &lt;/value&gt;
                    &lt;value&gt;
                        &lt;name&gt;Response Management&lt;/name&gt;
                        &lt;value&gt;ResponseManagement&lt;/value&gt;
                    &lt;/value&gt;
                    &lt;value&gt;
                        &lt;name&gt;External Redirect&lt;/name&gt;
                        &lt;value&gt;ExternalRedirect&lt;/value&gt;
                    &lt;/value&gt;
                    &lt;value&gt;
                        &lt;name&gt;Offline Applications&lt;/name&gt;
                        &lt;value&gt;OfflineApplications&lt;/value&gt;
                    &lt;/value&gt;
                &lt;/values&gt;
                &lt;type&gt;general&lt;/type&gt;
            &lt;/field&gt;
            &lt;field&gt;
                &lt;element&gt;text&lt;/element&gt;
                &lt;name&gt;stv_rid&lt;/name&gt;
                &lt;maxchars&gt;&lt;/maxchars&gt;
                &lt;type&gt;login&lt;/type&gt;
            &lt;/field&gt;
        &lt;/fields&gt;
    &lt;/response&gt;
    &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
<h1>
	Subscribing to portal</h1>
<p>To subscribe to portal need to send xml in the `data` variable using POST method.</p>
<h2>
	Request</h2>
<pre>
<code>
POST http://ws.idibu.com/ws/rest/v1/portals/123/subscribe?hash=<your hash>
</code></pre>
<pre>
<code type="xml">
&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;request&gt;
&lt;fields&gt;
&lt;field&gt;
&lt;name&gt;stv_method&lt;/name&gt;
&lt;value&gt;bla bla&lt;/value&gt;
&lt;/field&gt;
&lt;field&gt;
&lt;name&gt;stv_rid&lt;/name&gt;
&lt;value&gt;12345&lt;/value&gt;
&lt;/field&gt;
&lt;/fields&gt;
&lt;/request&gt;
&lt;/code&gt;
&lt;/pre&gt;
&lt;h2&gt;
	Response:&lt;/h2&gt;
&lt;pre&gt;
&lt;code type=&quot;xml&quot;&gt;
&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
    &lt;response&gt;
        &lt;message&gt;Portal added&lt;/message&gt;
    &lt;/response&gt;
    &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code>
</pre>
