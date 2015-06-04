

<p>Method allows you to return an excel report, filtered by data you have specified.</p>
<h1>
	Filtering options</h1>
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
				<p class="p2">from</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">Yes</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">YYYY-MM-DD date of begining of the gathered data, i.e. 2015-05-01</p>
			</td>
		</tr>
		<tr>
			<td class="td1" valign="middle">
				<p class="p2">to</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">Yes</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">YYYY-MM-DD date of begining of the gathered data, i.e. 2015-05-31.</p>
			</td>
		</tr>
				<tr>
			<td class="td1" valign="middle">
				<p class="p2">offices</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">Numeric IDs of the offices to be included in the report. If no offices, teams or profiles specified, report will be generated for all users with sorted under their respective offices and teams</p>
			</td>
		</tr>
						<tr>
			<td class="td1" valign="middle">
				<p class="p2">teams</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">Numeric IDs of the teams to be included in the report. If no offices, teams or profiles specified, report will be generated for all users with sorted under their respective offices and teams</p>
			</td>
		</tr>
						<tr>
			<td class="td1" valign="middle">
				<p class="p2">profiles</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">Numeric IDs of the users to be included in the report. If no offices, teams or profiles specified, report will be generated for all users with sorted under their respective offices and teams</p>
			</td>
		</tr>
	</tbody>
</table>
<!--break-->
<h1>
	Example</h1>
<h2>
	Request</h2>
<pre>
<code>
http://ws.idibu.com/ws/rest/v1/applicants/123/set-status?hash=<your hash>&status=Keep%20on%20file&responder=Yes
</code></pre>
<h2>
	Response</h2>
<pre>
<code type="xml">
&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
  &lt;response&gt;
    &lt;messsage&gt;Status updated&lt;/messsage&gt;
  &lt;/response&gt;
  &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
