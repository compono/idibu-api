<p>Method creates new client account in idibu system. <b>Available only for idibu partners</b></p>
<h1>
	Parameters</h1>
<p>To receive your exempt id (also known as partner ID) and the partner password, you will need to contact us!</p>
<h1>
	Example of adding a new account</h1>
<h2>
	Request</h2>
<pre>
<code>
POST http://ws.idibu.com/ws/rest/v1/service/newaccount?idibupartner=yes
</code>
<code type="xml">
&lt;?xml version=&quot;1.0&quot;?&gt;
&lt;idibu&gt;
  &lt;firstname&gt;Firstname&lt;/firstname&gt;
  &lt;lastname&gt;Lastname&lt;/lastname&gt;
  &lt;email&gt;email@test.com&lt;/email&gt;
  &lt;username&gt;user2&lt;/username&gt;
  &lt;password&gt;pas123&lt;/password&gt;
  &lt;company-name&gt;company&lt;/company-name&gt;
  &lt;phone&gt;123465&lt;/phone&gt;
  &lt;partner-password&gt;S0meP4rtn3rP4ssw0rd1sH3r3&lt;/partner-password&gt;
  &lt;user-number&gt;5&lt;/user-number&gt;
  &lt;renewal-date&gt;2012-05-05&lt;/renewal-date&gt;
  &lt;exempt-id&gt;1&lt;/exempt-id&gt;
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
    &lt;message&gt;New client successfully created&lt;/message&gt;
    &lt;client-hash&gt;373ed1cdfac5168e61d6dcea98d48f56&lt;/client-hash&gt;
    &lt;client-id&gt;1000916&lt;/client-id&gt;
    &lt;member-id&gt;1546&lt;/member-id&gt;
  &lt;/response&gt;
  &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code>
</pre>
