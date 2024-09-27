<p>Method shows/sets user quotas.<br/>
	<code>quota</code> is the amount of quotas.<br/>
	<code>limit</code> is the amount to which the quotas reset after the specified period (see <a href="https://github.com/oneworldmarket/idibu-api/blob/master/webservices/quota-management/add-quota-to-portal.md" target="_blank">add-quota-to-portal<a/>).</p>
<h1>Parameters</h1>
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
		<tr>
			<td class="td1" valign="middle">
				<p class="p2">hideEmpty</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">If <code>true</code>, users, teams and offices that have no quotas set will not be displayed in the response.</p>
			</td>
		</tr>
	</tbody>
</table>
<h1>Show user quotas</h1>
<h2>Example</h2>
<h3>Request</h3>
<pre><code>https://ws.idibu.com/ws/rest/v1/quotas/517/users?hash=YOUR_HASH</code></pre>
<h2>Response</h2>
<pre><code type="xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
    &lt;response&gt;
        &lt;quotas&gt;
            &lt;quota&gt;
                &lt;user-id&gt;485&lt;/user-id&gt;
                &lt;quota&gt;100&lt;/quota&gt;
                &lt;limit&gt;50&lt;/limit&gt;
		&lt;remaining&gt;85&lt;/remaining&gt;
                &lt;posted&gt;15&lt;/posted&gt;
            &lt;/quota&gt;
            &lt;quota&gt;
                &lt;user-id&gt;856&lt;/user-id&gt;
                &lt;quota&gt;1&lt;/quota&gt;
                &lt;limit&gt;&lt;/limit&gt;
		&lt;/remaining&gt;
                &lt;/posted&gt;
            &lt;/quota&gt;
            &lt;quota&gt;
                &lt;user-id&gt;1017&lt;/user-id&gt;
                &lt;quota&gt;1&lt;/quota&gt;
                &lt;limit&gt;&lt;/limit&gt;
		&lt;/remaining&gt;
                &lt;/posted&gt;
            &lt;/quota&gt;
            &lt;quota&gt;
                &lt;user-id&gt;1058&lt;/user-id&gt;
                &lt;quota&gt;3&lt;/quota&gt;
                &lt;limit&gt;5&lt;/limit&gt;
		&lt;/remaining&gt;
                &lt;/posted&gt;
            &lt;/quota&gt;
            &lt;quota&gt;
                &lt;user-id&gt;1066&lt;/user-id&gt;
                &lt;quota&gt;5&lt;/quota&gt;
                &lt;limit&gt;&lt;/limit&gt;
		&lt;/remaining&gt;
                &lt;/posted&gt;
            &lt;/quota&gt;
            &lt;quota&gt;
                &lt;user-id&gt;1101&lt;/user-id&gt;
                &lt;quota&gt;4&lt;/quota&gt;
                &lt;limit&gt;&lt;/limit&gt;
		&lt;remaining&gt;2&lt;/remaining&gt;
                &lt;posted&gt;2&lt;/posted&gt;
            &lt;/quota&gt;
            &lt;quota&gt;
                &lt;user-id&gt;1168&lt;/user-id&gt;
                &lt;quota&gt;3&lt;/quota&gt;
                &lt;limit&gt;0&lt;/limit&gt;
		&lt;/remaining&gt;
                &lt;/posted&gt;
            &lt;/quota&gt;
            &lt;quota&gt;
                &lt;user-id&gt;1198&lt;/user-id&gt;
                &lt;quota&gt;2&lt;/quota&gt;
                &lt;limit&gt;&lt;/limit&gt;
		&lt;/remaining&gt;
                &lt;/posted&gt;
            &lt;/quota&gt;
        &lt;/quotas&gt;
        &lt;total&gt;8&lt;/total&gt;
    &lt;/response&gt;
    &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
<h1>Set user quotas</h1>
<p>To set quotas, please provide <code>data</code> parameter containig an xml as shown in the example below.</p>
<p>For *slots* type of quotas, <code>limit</code> parameter in xml can be omitted.</p>
<h2>Example</h2>
<h3>Data posted</h3>
<pre><code>POST https://ws.idibu.com/ws/rest/v1/quotas/517/users?hash=YOUR_HASH</code></pre>
<pre><code type="xml">&lt;?xml version=&quot;1.0&quot;?&gt;
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
</code></pre>
<h2>Response</h2>
<pre>
<code type="xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
    &lt;response&gt;
        &lt;message&gt;Quota set&lt;/message&gt;
    &lt;/response&gt;
    &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
