_**This document is outdated. Please refer to the new version [HERE](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/service-management/service-management-webservice.md).**_

<details>
 <summary><i>Show me anyway</i></summary>

<p>Method adds new idibu services to the specified account (specified by hash). <b>Available only for idibu partners</b></p>
<h1>
	Parameters</h1>
<p>No additional parameters for this request</p>
<h2>Request</h2>
<pre>
<code>POST http://ws.idibu.com/ws/rest/v1/service/add?idibupartner=yes</code>
<code type="xml">
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
<h2>Response</h2>
<pre>
<code type="xml">
&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot;?&gt;
&lt;idibu&gt;
&lt;response&gt;
   &lt;message&gt;Service added!&lt;/message&gt;
&lt;/response&gt;
&lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code>
</pre>
</details>
