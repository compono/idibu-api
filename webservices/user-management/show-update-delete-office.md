<p>Method shows/edits/removes office</p>
<ul>
	<li>GET - view office information/settings</li>
	<li>POST - edit office settings</li>
	<li>DELETE - remove office</li>
</ul>
<h1>Parameters</h1>
<p>No additional parameters</p>
<h1>Getting office information</h1>
<p>Returns selected office's data (office 1234567 in the example).</p>
<h2>Example</h2>
<h3>Request</h3>
<pre><code>GET http://ws.idibu.com/ws/rest/v1/offices/1234567?hash=YOUR_HASH</code></pre>
<h3>Response</h3>
<pre><code type="xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
	&lt;response&gt;
		&lt;id&gt;1234567&lt;/id&gt;
		&lt;name&gt;Test office&lt;/name&gt;
		&lt;contacts&gt;
			&lt;address&gt;xxxxx&lt;/address&gt;
			&lt;address-line1&gt;yyyyy&lt;/address-line1&gt;
			&lt;address-line2&gt;zzzzz&lt;/address-line2&gt;
			&lt;address-line3/&gt;
			&lt;country&gt;United Kingdom&lt;/country&gt;
			&lt;postcode&gt;12345&lt;/postcode&gt;
			&lt;email&gt;test@test.com&lt;/email&gt;
			&lt;phone&gt;123 456 789&lt;/phone&gt;
			&lt;fax/&gt;
			&lt;www&gt;www.idibu.com&lt;/www&gt;
			&lt;company-name&gt;Test Company&lt;/company-name&gt;
			&lt;need-authorization&gt;No&lt;/need-authorization&gt;
		&lt;/contacts&gt;
	&lt;/response&gt;
	&lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
<h1>Updating office information</h1>
<p>To update office information, pass an xml in the <code>data</code> parameter. Any field or block can be omitted - pass only the fields which need updating (office 1234567 in the example).</p>
<h2>Example</h2>
<h3>Posted data</h3>
<pre><code>POST http://ws.idibu.com/ws/rest/v1/offices/1234567?hash=YOUR_HASH</code></pre>
<pre><code type="xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot;?&gt;
&lt;idibu&gt;
	&lt;name&gt;Test office&lt;/name&gt;
	&lt;contacts&gt;
		&lt;address&gt;xxxxx&lt;/address&gt;
		&lt;address-line1&gt;yyyyy&lt;/address-line1&gt;
		&lt;address-line2&gt;zzzzz&lt;/address-line2&gt;
		&lt;address-line3/&gt;
		&lt;country&gt;United Kingdom&lt;/country&gt;
		&lt;postcode&gt;12345&lt;/postcode&gt;
		&lt;email&gt;test@test.com&lt;/email&gt;
		&lt;phone&gt;123 456 789&lt;/phone&gt;
		&lt;fax/&gt;
		&lt;www&gt;www.idibu.com&lt;/www&gt;
		&lt;company-name&gt;Test Company&lt;/company-name&gt;
		&lt;need-authorization&gt;No&lt;/need-authorization&gt;
	&lt;/contacts&gt;
&lt;/idibu&gt;
</code></pre>
<h3>Response</h3>
<pre><code type="xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
	&lt;response&gt;
		&lt;message&gt;Office updated&lt;/message&gt;
	&lt;/response&gt;
	&lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
<h1>Deleting an office</h1>
<p>To delete an office, use a DELETE request (office 1234567 in the example)</p>
<h2>Example</h2>
<h3>Request</h3>
<pre><code>DELETE http://ws.idibu.com/ws/rest/v1/offices/1234567?hash=YOUR_HASH</code></pre>
<h3>Response</h3>
<pre>
<code type="xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
    &lt;response&gt;
        &lt;message&gt;Office deleted&lt;/message&gt;
    &lt;/response&gt;
    &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
