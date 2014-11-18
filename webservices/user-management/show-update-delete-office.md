<p>Method shows/edits/removes office</p>
<ul>
	<li>
		GET - view office information/settings</li>
	<li>
		POST - edit office settings</li>
	<li>
		DELETE - remove office</li>
</ul>
<h1>
	Parameters</h1>
<p>No additional parameters</p>
<h1>
	Getting office information</h1>
<p>Return office information</p>
<h2>
	Example</h2>
<h3>
	Request</h3>
<pre>
<code>
http://ws.idibu.com/ws/rest/v1/offices/33000171?hash=<your hash>
</code></pre>
<h3>
	Response</h3>
<pre>
<code type="xml">
&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
    &lt;response&gt;
        &lt;id&gt;33000170&lt;/id&gt;
        &lt;name&gt;moldova&lt;/name&gt;
        &lt;contacts&gt;&lt;address&gt;xxx
xx
xxx, xxx
xxxxx&lt;/address&gt;
            &lt;address-line1&gt;xxx&lt;/address-line1&gt;
            &lt;address-line2&gt;xx&lt;/address-line2&gt;
            &lt;address-line3&gt;xxx&lt;/address-line3&gt;
            &lt;country&gt;xxx&lt;/country&gt;
            &lt;postcode&gt;xxxxx&lt;/postcode&gt;
            &lt;email&gt;x@x.pl&lt;/email&gt;
            &lt;phone&gt;345678&lt;/phone&gt;
            &lt;fax&gt;456789&lt;/fax&gt;
            &lt;www&gt;www.w.ww&lt;/www&gt;
        &lt;/contacts&gt;
    &lt;/response&gt;
    &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
<h1>
	Updating office information</h1>
<p>To update office information need to pass xml of the same format as in response to the GET request in data parameter. Any field or block can be omited, pass in the xml only those fields which you need update.</p>
<h2>
	Example</h2>
<h3>
	Posted data</h3>
<pre>
<code>
POST http://ws.idibu.com/ws/rest/v1/offices/33000170?hash=<your hash>
</code></pre>
&lt;?xml version=&quot;1.0&quot;?&gt;
&lt;idibu&gt;
&lt;name&gt; new office name &lt;/name&gt;
&lt;contacts&gt;
&lt;email&gt;test@example.com&lt;/email&gt;
&lt;/contacts&gt;
&lt;/idibu&gt;
<h3>
	Response</h3>
<pre>
<code type="xml">
&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
    &lt;response&gt;
        &lt;message&gt;Office updated&lt;/message&gt;
    &lt;/response&gt;
    &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
<h1>
	Deleting office</h1>
<p>To delete an office use a DELETE request</p>
<h2>
	Example</h2>
<h3>
	Request</h3>
<pre>
<code>
DELETE http://ws.idibu.com/ws/rest/v1/offices/33000170?hash=<your hash>
</code></pre>
<h3>
	Response</h3>
<pre>
<code type="xml">
&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
    &lt;response&gt;
        &lt;message&gt;Office deleted&lt;/message&gt;
    &lt;/response&gt;
    &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
