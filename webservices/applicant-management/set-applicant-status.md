<p>Method returns applicant list</p>
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
				<p class="p2">status</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">Yes</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">New applicant status</p>
			</td>
		</tr>
		<tr>
			<td class="td1" valign="middle">
				<p class="p2">responder</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">Allowed Value: &quot;Yes&quot;. If sent, responder will be sent only if it is defined for the Status.</p>
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
