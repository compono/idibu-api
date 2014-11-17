<p>Method shows/sets user quotas</p>
<h1>
	Parameters</h1>
<table cellpadding="2" cellspacing="0" class="t1" width="1084.0">
	<thead>
		<tr>
			<th class="td1" scope="col" valign="middle">
				<p class="p1"><b>Parameter Name</b></p>
			</th>
			<th class="td2" scope="col" valign="middle">
				<p class="p1"><b>Required?</b></p>
			</th>
			<th class="td3" scope="col" valign="middle">
				<p class="p1"><b>Notes</b></p>
			</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td class="td1" valign="middle">
				<p class="p2">offset</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">numeric offset from where to fetch user quotas, default is 0</p>
			</td>
		</tr>
		<tr>
			<td class="td1" valign="middle">
				<p class="p2">count</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">number of user quotas to return in response, default is 10</p>
			</td>
		</tr>
		<tr>
			<td class="td1" valign="middle">
				<p class="p2">team-id</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">filter user quotas by team</p>
			</td>
		</tr>
		<tr>
			<td class="td1" valign="middle">
				<p class="p2">office-id</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">filter user quotas by office</p>
			</td>
		</tr>
	</tbody>
</table>
<h1>
	Example</h1>
<h2>
	Request</h2>
<pre>
<code>
http://ws.idibu.com/ws/rest/v1/quotas/517/users?hash=<your hash>
</code></pre>
<h2>
	Response</h2>
<pre>
<code type="xml">
&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
    &lt;response&gt;
        &lt;quotas&gt;
            &lt;quota&gt;
                &lt;user-id&gt;485&lt;/user-id&gt;
                &lt;quota&gt;1987&lt;/quota&gt;
                &lt;limit&gt;123&lt;/limit&gt;
            &lt;/quota&gt;
            &lt;quota&gt;
                &lt;user-id&gt;856&lt;/user-id&gt;
                &lt;quota&gt;1&lt;/quota&gt;
                &lt;limit&gt;&lt;/limit&gt;
            &lt;/quota&gt;
            &lt;quota&gt;
                &lt;user-id&gt;1017&lt;/user-id&gt;
                &lt;quota&gt;1&lt;/quota&gt;
                &lt;limit&gt;&lt;/limit&gt;
            &lt;/quota&gt;
            &lt;quota&gt;
                &lt;user-id&gt;1058&lt;/user-id&gt;
                &lt;quota&gt;3&lt;/quota&gt;
                &lt;limit&gt;5&lt;/limit&gt;
            &lt;/quota&gt;
            &lt;quota&gt;
                &lt;user-id&gt;1066&lt;/user-id&gt;
                &lt;quota&gt;5&lt;/quota&gt;
                &lt;limit&gt;&lt;/limit&gt;
            &lt;/quota&gt;
            &lt;quota&gt;
                &lt;user-id&gt;1101&lt;/user-id&gt;
                &lt;quota&gt;4&lt;/quota&gt;
                &lt;limit&gt;&lt;/limit&gt;
            &lt;/quota&gt;
            &lt;quota&gt;
                &lt;user-id&gt;1168&lt;/user-id&gt;
                &lt;quota&gt;3&lt;/quota&gt;
                &lt;limit&gt;0&lt;/limit&gt;
            &lt;/quota&gt;
            &lt;quota&gt;
                &lt;user-id&gt;1198&lt;/user-id&gt;
                &lt;quota&gt;2&lt;/quota&gt;
                &lt;limit&gt;&lt;/limit&gt;
            &lt;/quota&gt;
        &lt;/quotas&gt;
        &lt;total&gt;8&lt;/total&gt;
    &lt;/response&gt;
    &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
<h1>
	Set user quotas</h1>
<p>To set quotas we have to provide *data* parameter with xml as shown in example.</p>
<p>For *slots* type of quotas *limit* parameter in xml can be omitted.</p>
<h1>
	Example</h1>
<h2>
	Data posted</h2>
<pre>
<code>
POST http://ws.idibu.com/ws/rest/v1/quotas/517/users?hash=<your hash>
</code></pre>
<pre>
<code type="xml">
&lt;?xml version=&quot;1.0&quot;?&gt;
&lt;idibu&gt;
&lt;quota&gt;
    &lt;user-id&gt;33000171&lt;/user-id&gt;
    &lt;quota&gt;1&lt;/quota&gt;
    &lt;limit&gt;&lt;/limit&gt;
&lt;/quota&gt;
&lt;quota&gt;
    &lt;user-id&gt;33000172&lt;/user-id&gt;
    &lt;quota&gt;2&lt;/quota&gt;
    &lt;limit&gt;3&lt;/limit&gt;
&lt;/quota&gt;
&lt;/idibu&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;h2&gt;
	Response&lt;/h2&gt;
&lt;pre&gt;
&lt;code type=&quot;xml&quot;&gt;
&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
    &lt;response&gt;
        &lt;message&gt;Quota set&lt;/message&gt;
    &lt;/response&gt;
    &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
