<p>Method removes idibu services from the specified account (specified by hash). <b>Available only for idibu partners</b></p>
<h1>
	Parameters</h1>
<p>No additional parameters for this request</p>
<h1>
	Example of removing services</h1>
<p>Available service types: aptrack, leadwatch, cvpreview, apsearch</p>
<h2>
	Request</h2>
<pre>
<code>
POST http://ws.idibu.com/ws/rest/v1/service/remove?idibupartner=yes
</code>
<code type="xml">
&lt;?xml version=&quot;1.0&quot;?&gt;
&lt;idibu&gt;
  &lt;partner-password&gt;123&lt;/partner-password&gt;
  &lt;exempt-id&gt;0&lt;/exempt-id&gt;
  &lt;client-hash&gt;373ed1cdfac5168e61d6dcea98d48f56&lt;/client-hash&gt;
  &lt;services&gt;
      &lt;service&gt;aptrack&lt;/service&gt;
  &lt;/services&gt;
&lt;/idibu&gt;
</code>
</pre>
<h2>
	Response</h2>
<pre>
&lt;code type=&quot;xml&quot;&gt;
&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
  &lt;response&gt;
    &lt;message&gt;Services removed&lt;/message&gt;
  &lt;/response&gt;
  &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code>
</pre>
