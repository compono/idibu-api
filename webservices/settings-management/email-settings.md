<p>Method gets or sets email settings for an account</p>
<h1>
	Parameters</h1>
<p>No additional parameters for this request</p>
<h1>
	Possible values</h1>
<table>
	<tbody>
		<tr>
			<th>
				Param</th>
			<th>
				Values</th>
		</tr>
		<tr>
			<td>
				type</td>
			<td>
				default, custom. Default - use idibu mail server. Custom - define your own mail server settings</td>
		</tr>
		<tr>
			<td>
				name</td>
			<td>
				Name, which will be used in From header</td>
		</tr>
		<tr>
			<td>
				host</td>
			<td>
				Host address of your server</td>
		</tr>
		<tr>
			<td>
				port</td>
			<td>
				Port address of smtp service, should be numeric</td>
		</tr>
		<tr>
			<td>
				smtp-auth</td>
			<td>
				yes, no. Yes - if server requires authentification, no otherwise</td>
		</tr>
		<tr>
			<td>
				username</td>
			<td>
				User name</td>
		</tr>
		<tr>
			<td>
				password</td>
			<td>
				Password</td>
		</tr>
		<tr>
			<td>
				smtp-secure</td>
			<td>
				no, tls, ssl</td>
		</tr>
		<tr>
			<td>
				email &gt; type</td>
			<td>
				profile, custom. Profile - From address will be taken from profile. Custom - will be used static email address for all profiles, custom email address should be provided in email &gt; email</td>
		</tr>
		<tr>
			<td>
				email &gt; email</td>
			<td>
				Static email address used for type <i>custom</i></td>
		</tr>
	</tbody>
</table>
<h1>
	Example of getting settings</h1>
<h2>
	Request</h2>
<pre>
<code>
http://ws.idibu.com/ws/rest/v1/settings/email?hash=<your hash>
</code></pre>
<h2>
	Response</h2>
<pre>
<code type="xml">
&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
  &lt;response&gt;
    &lt;type&gt;custom&lt;/type&gt;
    &lt;name&gt;&lt;/name&gt;
    &lt;host&gt;&lt;/host&gt;
    &lt;port&gt;&lt;/port&gt;
    &lt;smtp-auth&gt;no&lt;/smtp-auth&gt;
    &lt;username&gt;&lt;/username&gt;
    &lt;password&gt;&lt;/password&gt;
    &lt;smtp-secure&gt;&lt;/smtp-secure&gt;
    &lt;email&gt;
      &lt;type&gt;custom&lt;/type&gt;
      &lt;email&gt;vitaly@idibu.com&lt;/email&gt;&lt;/email&gt;
    &lt;/response&gt;
    &lt;status&gt;success&lt;/status&gt;
  &lt;/idibu&gt;
</code></pre>
<h1>
	Example of setting settings</h1>
<h2>
	Request</h2>
<pre>
<code>
POST http://ws.idibu.com/ws/rest/v1/settings/email?hash=<your hash>
</code>
<code type="xml">
&lt;?xml version=&quot;1.0&quot;?&gt;
&lt;idibu&gt;
  &lt;type&gt;custom&lt;/type&gt;
  &lt;email&gt;
    &lt;type&gt;custom&lt;/type&gt;
    &lt;email&gt;vitaly@idibu.com&lt;/email&gt;
  &lt;/email&gt;
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
    &lt;message&gt;Settings updated&lt;/message&gt;
  &lt;/response&gt;
  &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code>
</pre>
