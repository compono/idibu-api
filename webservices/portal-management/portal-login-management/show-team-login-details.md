<p>Method returns team logins for selected portal</p>
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
				<p class="p2">numeric offset from where to fetch teams, default is 0</p>
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
				<p class="p2">number of teams to return in response, default is 10</p>
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
				<p class="p2">select concrete team</p>
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
				<p class="p2">filter teams by office</p>
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
https://ws.idibu.com/ws/rest/v1/portals/517/team-logins?hash=<your hash>
</code></pre>
<h2>
	Response</h2>
<pre>
<code type="xml">
&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
    &lt;response&gt;
        &lt;teams&gt;
            &lt;team&gt;
                &lt;id&gt;33000171&lt;/id&gt;
                &lt;fields&gt;
                    &lt;field&gt;
                        &lt;name&gt;userName&lt;/name&gt;
                        &lt;value&gt;tiraspol&lt;/value&gt;
                    &lt;/field&gt;
                    &lt;field&gt;
                        &lt;name&gt;userPassword&lt;/name&gt;
                        &lt;value&gt;pwd&lt;/value&gt;
                    &lt;/field&gt;
                &lt;/fields&gt;
            &lt;/team&gt;
            &lt;team&gt;
                &lt;id&gt;33000179&lt;/id&gt;
                &lt;fields&gt;
                    &lt;field&gt;
                        &lt;name&gt;userName&lt;/name&gt;
                        &lt;value&gt;&lt;/value&gt;
                    &lt;/field&gt;
                    &lt;field&gt;
                        &lt;name&gt;userPassword&lt;/name&gt;
                        &lt;value&gt;&lt;/value&gt;
                    &lt;/field&gt;
                &lt;/fields&gt;
            &lt;/team&gt;
            &lt;team&gt;
                &lt;id&gt;33000183&lt;/id&gt;
                &lt;fields&gt;
                    &lt;field&gt;
                        &lt;name&gt;userName&lt;/name&gt;
                        &lt;value&gt;&lt;/value&gt;
                    &lt;/field&gt;
                    &lt;field&gt;
                        &lt;name&gt;userPassword&lt;/name&gt;
                        &lt;value&gt;&lt;/value&gt;
                    &lt;/field&gt;
                &lt;/fields&gt;
            &lt;/team&gt;
        &lt;/teams&gt;
        &lt;total&gt;3&lt;/total&gt;
    &lt;/response&gt;
    &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
