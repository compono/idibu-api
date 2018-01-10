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
				<p class="p2">filter portals by categories (see <a href="https://github.com/oneworldmarket/idibu-api/blob/master/webservices/portal-management/portal-details/get-portal-category-list.md" target="_blank">get-portal-category-list</a>); multiple allowed (comma-separated)</p>
			</td>
		</tr>
		<tr>
			<td class="td1" valign="middle">
				<p class="p2">filter_country</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">filter portals by countries (see <a href="https://github.com/oneworldmarket/idibu-api/blob/master/webservices/portal-management/portal-details/get-portal-country-list.md" target="_blank">get-portal-country-list</a>); multiple allowed (comma-separated); you can use both full country names and 3-letter ISO codes</p>
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
http://ws.idibu.com/ws/rest/v1/portals/all?hash=YOUR_HASH&count=5&filter_country=USA,United+Kingdom&filter_tags=free
</code></pre>
<h2>
	Response</h2>
<pre>
<code type="xml">&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
	&lt;response&gt;
		&lt;portals&gt;
			&lt;portal&gt;
				&lt;id&gt;250&lt;/id&gt;
				&lt;name&gt;4 Accountancy Jobs&lt;/name&gt;
				&lt;url&gt;www.4accountancyjobs.com&lt;/url&gt;
				&lt;logo&gt;4accountancy.jpg&lt;/logo&gt;
				&lt;tags&gt;free, accountancy,&lt;/tags&gt;
				&lt;supports-aptrack&gt;yes&lt;/supports-aptrack&gt;
				&lt;supports-delete&gt;no&lt;/supports-delete&gt;
				&lt;published&gt;yes&lt;/published&gt;
				&lt;country&gt;GBR&lt;/country&gt;
			&lt;/portal&gt;
			&lt;portal&gt;
				&lt;id&gt;252&lt;/id&gt;
				&lt;name&gt;4 Construction Jobs&lt;/name&gt;
				&lt;url&gt;www.4constructionjobs.co.uk&lt;/url&gt;
				&lt;logo&gt;4constructionjobs.jpg&lt;/logo&gt;
				&lt;tags&gt;free, construction,&lt;/tags&gt;
				&lt;supports-aptrack&gt;yes&lt;/supports-aptrack&gt;
				&lt;supports-delete&gt;no&lt;/supports-delete&gt;
				&lt;published&gt;yes&lt;/published&gt;
				&lt;country&gt;GBR&lt;/country&gt;
			&lt;/portal&gt;
			&lt;portal&gt;
				&lt;id&gt;254&lt;/id&gt;
				&lt;name&gt;4 Defence Jobs&lt;/name&gt;
				&lt;url&gt;www.4defencejobs.com&lt;/url&gt;
				&lt;logo&gt;4defencejobs.jpg&lt;/logo&gt;
				&lt;tags&gt;free, defence,&lt;/tags&gt;
				&lt;supports-aptrack&gt;yes&lt;/supports-aptrack&gt;
				&lt;supports-delete&gt;no&lt;/supports-delete&gt;
				&lt;published&gt;yes&lt;/published&gt;
				&lt;country&gt;GBR&lt;/country&gt;
			&lt;/portal&gt;
			&lt;portal&gt;
				&lt;id&gt;255&lt;/id&gt;
				&lt;name&gt;4 Engineering Jobs&lt;/name&gt;
				&lt;url&gt;www.4engineeringjobs.com&lt;/url&gt;
				&lt;logo&gt;4engineeringjobs.jpg&lt;/logo&gt;
				&lt;tags&gt;free, engineering,&lt;/tags&gt;
				&lt;supports-aptrack&gt;yes&lt;/supports-aptrack&gt;
				&lt;supports-delete&gt;no&lt;/supports-delete&gt;
				&lt;published&gt;yes&lt;/published&gt;
				&lt;country&gt;GBR&lt;/country&gt;
			&lt;/portal&gt;
			&lt;portal&gt;
				&lt;id&gt;256&lt;/id&gt;
				&lt;name&gt;4 Engineers&lt;/name&gt;
				&lt;url&gt;www.4engineers.co.uk&lt;/url&gt;
				&lt;logo&gt;4engineers.jpg&lt;/logo&gt;
				&lt;tags&gt;free, engineering,&lt;/tags&gt;
				&lt;supports-aptrack&gt;yes&lt;/supports-aptrack&gt;
				&lt;supports-delete&gt;no&lt;/supports-delete&gt;
				&lt;published&gt;yes&lt;/published&gt;
				&lt;country&gt;GBR&lt;/country&gt;
			&lt;/portal&gt;
		&lt;/portals&gt;
		&lt;offset&gt;0&lt;/offset&gt;
		&lt;count&gt;5&lt;/count&gt;
		&lt;total&gt;53&lt;/total&gt;
	&lt;/response&gt;
	&lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
