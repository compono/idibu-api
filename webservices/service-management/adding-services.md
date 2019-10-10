<p>Method adds new idibu services to the specified account (specified by hash). <b>Available only for idibu partners</b></p>
<h1>
	Parameters</h1>
<p>No additional parameters for this request</p>
<h2>
	Request</h2>
<pre>
<code>
POST http://ws.idibu.com/ws/rest/v1/service/add?idibupartner=yes
</code>
&lt;code type=&quot;xml&quot;&gt;
&lt;?xml version=&quot;1.0&quot;?&gt;
&lt;idibu&gt;
      &lt;client-hash&gt;d7e573...&lt;/client-hash&gt;
      &lt;exempt-id&gt;18&lt;/exempt-id&gt;
      &lt;partner-password&gt;123456&lt;/partner-password&gt;
      &lt;username&gt;john_tester&lt;/username&gt;
      &lt;password&gt;test123&lt;/password&gt;
      &lt;services&gt;
            &lt;service&gt;aptrack&lt;/service&gt;
      &lt;/services&gt; 
&lt;/idibu&gt;
</code>
</pre>
<h2>
	Response</h2>
<pre>
<code type="xml">
&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
&lt;response&gt;
   &lt;message&gt;Client successfully updated&lt;/message&gt;
   &lt;client-hash&gt;[NEW HASH]&lt;/client-hash&gt;
   &lt;client-id&gt;1004339&lt;/client-id&gt;
   &lt;member-id&gt;4924&lt;/member-id&gt;
&lt;/response&gt;
&lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code>
</pre>
