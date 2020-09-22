_**This document is outdated. Please refer to the new version [HERE](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/service-management/service-management-webservice.md).**_

<details>
 <summary><i>Show me anyway</i></summary>
	
<p>Method lists idibu services for the specified account (specified by hash). <b>Available only for idibu partners</b></p>
<h1>
	Parameters</h1>
<p>No additional parameters for this request</p>
<h1>
	Example of viewing account services</h1>
<p>Available service types: aptrack, leadwatch, cvpreview, apsearch</p>
<h2>
	Request</h2>
<pre>
<code>
POST http://ws.idibu.com/ws/rest/v1/service/list?idibupartner=yes
</code>
<code type="xml">
&lt;?xml version=&quot;1.0&quot;?&gt;
&lt;idibu&gt;
  &lt;partner-password&gt;123&lt;/partner-password&gt;
  &lt;exempt-id&gt;0&lt;/exempt-id&gt;
  &lt;client-hash&gt;373ed1cdfac5168e61d6dcea98d48f56&lt;/client-hash&gt;
&lt;/idibu&gt;
</code>
</pre>
<h2>
	Response</h2>

```xml
<?xml version="1.0" encoding="utf8"?>
<idibu generator="idibu" version="1.0">
  <response>
    <services>
      <service>aptrack</service>
      <service>apsearch</service>
    </services>
  </response>
  <status>success</status>
</idibu>

```
</details>
