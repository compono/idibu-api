_**This document is outdated. Please refer to the new version [HERE](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/service-management/service-management-webservice.md).**_

<details>
 <summary><i>Show me anyway</i></summary>
	
<p>Method allows one to change account`s login details. This is for administrator login only. Mind that changing account logins will also change the login hash.<b>Available only for idibu partners</b></p>
<h2>
	Request</h2>
<pre>
<code>
POST http://ws.idibu.com/ws/rest/v1/service/updateaccount?idibupartner=yes
</code>
<code type="xml">
<?xml version="1.0"?>
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
<code type="xml">
&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
  &lt;response&gt;
    &lt;message&gt;Services added&lt;/message&gt;
  &lt;/response&gt;
  &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code>
</pre>
</details>
