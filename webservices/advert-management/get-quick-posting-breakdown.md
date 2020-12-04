_**This document is outdated. Please refer to the new version [HERE](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/advert-management/advert-management-webservice.md).**_

<details>
 <summary><i>Show me anyway</i></summary>
	
<p>Method returns all adverts for a client, which gives you brief information on what jobs were posted, which boards (with their current status) and what is their final expiry date. The returned data is limited to the last 6 months.
<h1 class="p1">
	Parameters</h1>
<table cellpadding="2" cellspacing="0" class="t1" width="1099.0">
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
				<p class="p2">format</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">You can choose to display only the currently live adverts (format=live)</p>
			</td>
		</tr>
	</tbody>
</table>
<h1 class="p3">
	Example</h1>
<h2>
	Request</h2>
<pre>


<code>
http://ws.idibu.com/ws/rest/v1/job-report?hash=<your hash>&format=live
</code></pre>
<h2>
	Response</h2>
<pre>


&lt;code type=&quot;xml&quot;&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
&lt;response&gt;
    &lt;jobs&gt;
        &lt;job id=&quot;37053733&quot;&gt;
            &lt;reference&gt;Example_ref&lt;/reference&gt;
            &lt;postings&gt;
                &lt;posting board_id=&quot;1501&quot;&gt;
                &lt;board_name&gt;JobUp.ch&lt;/board_name&gt;
                &lt;status&gt;live&lt;/status&gt;
                &lt;expiry&gt;2015-02-03 00:01:00&lt;/expiry&gt;
                &lt;/posting&gt;
            &lt;/postings&gt;
        &lt;/job&gt;
        &lt;job id=&quot;37053631&quot;&gt;
            &lt;reference&gt;Example_ref2&lt;/reference&gt;
            &lt;postings&gt;
                &lt;posting board_id=&quot;1501&quot;&gt;
                &lt;board_name&gt;JobUp.ch&lt;/board_name&gt;
                &lt;status&gt;deleted&lt;/status&gt;
                &lt;expiry&gt;2015-02-02 09:00:00&lt;/expiry&gt;
            &lt;/posting&gt;
        &lt;/postings&gt;
    &lt;/job&gt;&lt;/jobs&gt;
&lt;/response&gt;
&lt;/idibu&gt;</code></pre>

</details>
