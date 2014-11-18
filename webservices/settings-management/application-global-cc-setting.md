<p>In order to append an email address to which all incoming applications are forwarded to an account, please use the following:</p>
<h2>
	Request</h2>
<pre>
<code>
POST http://ws.idibu.com/ws/rest/v1/service/setccemail?idibupartner=yes
</code>
<code type="xml">
&lt;?xml version=&quot;1.0&quot;?&gt;
&lt;idibu&gt;
    &lt;client-hash&gt;2656a20(...)&lt;/client-hash&gt;
    &lt;exempt-id&gt;&lt;/exempt-id&gt;
    &lt;partner-password&gt;123&lt;/partner-password&gt;
    &lt;cc-email&gt;ccemail@just.hr&lt;/cc-email&gt;
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
   &lt;message&gt;Client`s central CC email set&lt;/message&gt;
   &lt;cc-email&gt;ccemail@just.hr&lt;/cc-email&gt;
&lt;/response&gt;
&lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code>
</pre>
<p>To remove the global CC email, simply provide a request with an empty ccemail field:</p>
<h2>
	Request</h2>
<pre>
<code>
POST http://ws.idibu.com/ws/rest/v1/service/setccemail?idibupartner=yes
</code>
<code type="xml">
&lt;?xml version=&quot;1.0&quot;?&gt;
&lt;idibu&gt;
    &lt;client-hash&gt;2656a20(...)&lt;/client-hash&gt;
    &lt;exempt-id&gt;&lt;/exempt-id&gt;
    &lt;partner-password&gt;123&lt;/partner-password&gt;
    &lt;cc-email&gt;&lt;/cc-email&gt;
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
   &lt;message&gt;Client`s central CC email set&lt;/message&gt;
   &lt;cc-email&gt;ccemail@just.hr&lt;/cc-email&gt;
&lt;/response&gt;
&lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code>
</pre>
<p>Finally you can double check the cc email set with:</p>
<h2>
	Request</h2>
<pre>
<code>
POST http://ws.idibu.com/ws/rest/v1/service/getccemail?idibupartner=yes
</code>
<code type="xml">
&lt;?xml version=&quot;1.0&quot;?&gt;
&lt;idibu&gt;
    &lt;client-hash&gt;2656a20(...)&lt;/client-hash&gt;
    &lt;exempt-id&gt;&lt;/exempt-id&gt;
    &lt;partner-password&gt;123&lt;/partner-password&gt;
&lt;/idibu&gt;
</code></pre>
<p>&nbsp;</p>
