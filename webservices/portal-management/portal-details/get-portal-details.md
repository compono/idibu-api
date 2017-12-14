<p>Method returns subscribed portals for client</p>
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
				<p class="p2">numeric offset from where to fetch adverts, default is 0</p>
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
				<p class="p2">number of adverts to return in response, default is 10</p>
			</td>
		</tr>
		<tr>
			<td class="td1" valign="middle">
				<p class="p2">filter_name</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">filter portals by name</p>
			</td>
		</tr>
		<tr>
			<td class="td1" valign="middle">
				<p class="p2">filter_tags</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">filter portals by tags (see <a href="https://github.com/oneworldmarket/idibu-api/blob/master/webservices/portal-management/portal-details/get-portal-category-list.md" target="_blank">get-portal-category-list</a>)</p>
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
http://ws.idibu.com/ws/rest/v1/portals/all?hash=<your hash>&count=5&filter_name=defence
</code></pre>
<h2>
	Response</h2>
<pre>
<code type="xml">
&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
    &lt;response&gt;
        &lt;portals&gt;
            &lt;portal&gt;
                &lt;id&gt;500&lt;/id&gt;
                &lt;name&gt;4 Teaching Jobs&lt;/name&gt;
                &lt;url&gt;www.4teachingjobs.net&lt;/url&gt;
                &lt;logo&gt;4te.jpg&lt;/logo&gt;
                &lt;tags&gt;free,
education,
&lt;/tags&gt;
            &lt;/portal&gt;
            &lt;portal&gt;
                &lt;id&gt;448&lt;/id&gt;
                &lt;name&gt;4 UK Jobs&lt;/name&gt;
                &lt;url&gt;www.4ukjobs.net&lt;/url&gt;
                &lt;logo&gt;4uk.jpg&lt;/logo&gt;
                &lt;tags&gt;general,
free,
&lt;/tags&gt;
            &lt;/portal&gt;
            &lt;portal&gt;
                &lt;id&gt;1041&lt;/id&gt;
                &lt;name&gt;4G Wireless Jobs&lt;/name&gt;
                &lt;url&gt;www.4gwirelessjobs.com&lt;/url&gt;
                &lt;logo&gt;4gw.jpg&lt;/logo&gt;
                &lt;tags&gt;information_technology,
&lt;/tags&gt;
            &lt;/portal&gt;
            &lt;portal&gt;
                &lt;id&gt;204&lt;/id&gt;
                &lt;name&gt;Aberdeen-Jobs&lt;/name&gt;
                &lt;url&gt;www.aberdeen-jobs.com&lt;/url&gt;
                &lt;logo&gt;aberdeenjobs2.jpg&lt;/logo&gt;
                &lt;tags&gt;regional,
&lt;/tags&gt;
            &lt;/portal&gt;
            &lt;portal&gt;
                &lt;id&gt;190&lt;/id&gt;
                &lt;name&gt;Access-Science Jobs&lt;/name&gt;
                &lt;url&gt;www.access-sciencejobs.co.uk&lt;/url&gt;
                &lt;logo&gt;accscie3.jpg&lt;/logo&gt;
                &lt;tags&gt;science,
&lt;/tags&gt;
            &lt;/portal&gt;
            &lt;portal&gt;
                &lt;id&gt;64&lt;/id&gt;
                &lt;name&gt;Accountancy Age Jobs&lt;/name&gt;
                &lt;url&gt;www.accountancyagejobs.com&lt;/url&gt;
                &lt;logo&gt;accountancyagejobs.jpg&lt;/logo&gt;
                &lt;tags&gt;accountancy,
&lt;/tags&gt;
            &lt;/portal&gt;
            &lt;portal&gt;
                &lt;id&gt;393&lt;/id&gt;
                &lt;name&gt;Accountancy Job Board&lt;/name&gt;
                &lt;url&gt;www.accountancyjobboard.com&lt;/url&gt;
                &lt;logo&gt;accjb2.jpg&lt;/logo&gt;
                &lt;tags&gt;free,
accountancy,
&lt;/tags&gt;
            &lt;/portal&gt;
            &lt;portal&gt;
                &lt;id&gt;1052&lt;/id&gt;
                &lt;name&gt;Accountant Jobs.ie&lt;/name&gt;
                &lt;url&gt;www.accountantjobs.ie&lt;/url&gt;
                &lt;logo&gt;accountantjie.jpg&lt;/logo&gt;
                &lt;tags&gt;accountancy,
&lt;/tags&gt;
            &lt;/portal&gt;
            &lt;portal&gt;
                &lt;id&gt;380&lt;/id&gt;
                &lt;name&gt;Accounting jobs&lt;/name&gt;
                &lt;url&gt;accountingjobs.co.uk&lt;/url&gt;
                &lt;logo&gt;accountingjobs.jpg&lt;/logo&gt;
                &lt;tags&gt;accountancy,
&lt;/tags&gt;
            &lt;/portal&gt;
            &lt;portal&gt;
                &lt;id&gt;588&lt;/id&gt;
                &lt;name&gt;Actuary Jobs&lt;/name&gt;
                &lt;url&gt;www.theactuaryjobs.co.uk&lt;/url&gt;
                &lt;logo&gt;actuaryjobs.jpg&lt;/logo&gt;
                &lt;tags&gt;general,
&lt;/tags&gt;
            &lt;/portal&gt;
        &lt;/portals&gt;
        &lt;offset&gt;20&lt;/offset&gt;
        &lt;count&gt;10&lt;/count&gt;
        &lt;total&gt;503&lt;/total&gt;
    &lt;/response&gt;
    &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
