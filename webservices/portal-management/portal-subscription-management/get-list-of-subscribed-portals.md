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
				<p class="p2">numeric offset from where to fetch portals, default is 0</p>
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
				<p class="p2">number of portals to return, default is 10</p>
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
http://ws.idibu.com/ws/rest/v1/portals/subscribed?hash=YOUR_HASH&count=5&filter_country=GBR,United+States&filter_tags=general
</code></pre>
<h2>
	Response</h2>
<pre>
<code type="xml">&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
	&lt;response&gt;
		&lt;portals&gt;
			&lt;portal&gt;
				&lt;id&gt;39&lt;/id&gt;
				&lt;name&gt;CV - Library&lt;/name&gt;
				&lt;url&gt;www.cv-library.co.uk&lt;/url&gt;
				&lt;logo&gt;cvlibrarylogo_ibidu.gif&lt;/logo&gt;
				&lt;tags&gt;general, all,&lt;/tags&gt;
				&lt;supports-aptrack&gt;yes&lt;/supports-aptrack&gt;
				&lt;supports-delete&gt;yes&lt;/supports-delete&gt;
				&lt;published&gt;yes&lt;/published&gt;
				&lt;country&gt;GBR&lt;/country&gt;
			&lt;/portal&gt;
			&lt;portal&gt;
				&lt;id&gt;1185&lt;/id&gt;
				&lt;name&gt;Indeed&lt;/name&gt;
				&lt;url&gt;www.indeed.com&lt;/url&gt;
				&lt;logo&gt;indeed2.jpg&lt;/logo&gt;
				&lt;tags&gt;general,&lt;/tags&gt;
				&lt;supports-aptrack&gt;yes&lt;/supports-aptrack&gt;
				&lt;supports-delete&gt;yes&lt;/supports-delete&gt;
				&lt;published&gt;yes&lt;/published&gt;
				&lt;country&gt;GBR&lt;/country&gt;
			&lt;/portal&gt;
			&lt;portal&gt;
				&lt;id&gt;1185&lt;/id&gt;
				&lt;name&gt;Indeed&lt;/name&gt;
				&lt;url&gt;www.indeed.com&lt;/url&gt;
				&lt;logo&gt;indeed2.jpg&lt;/logo&gt;
				&lt;tags&gt;general,&lt;/tags&gt;
				&lt;supports-aptrack&gt;yes&lt;/supports-aptrack&gt;
				&lt;supports-delete&gt;yes&lt;/supports-delete&gt;
				&lt;published&gt;yes&lt;/published&gt;
				&lt;country&gt;USA&lt;/country&gt;
			&lt;/portal&gt;
			&lt;portal&gt;
				&lt;id&gt;41&lt;/id&gt;
				&lt;name&gt;JobSite.co.uk&lt;/name&gt;
				&lt;url&gt;www.jobsite.co.uk&lt;/url&gt;
				&lt;logo&gt;jobsite2.jpg&lt;/logo&gt;
				&lt;tags&gt;general, all,&lt;/tags&gt;
				&lt;supports-aptrack&gt;yes&lt;/supports-aptrack&gt;
				&lt;supports-delete&gt;yes&lt;/supports-delete&gt;
				&lt;published&gt;yes&lt;/published&gt;
				&lt;country&gt;GBR&lt;/country&gt;
			&lt;/portal&gt;
			&lt;portal&gt;
				&lt;id&gt;253&lt;/id&gt;
				&lt;name&gt;Monster Test&lt;/name&gt;
				&lt;url&gt;www.freespace.com&lt;/url&gt;
				&lt;logo&gt;monstertest2014.png&lt;/logo&gt;
				&lt;tags&gt;general, all,&lt;/tags&gt;
				&lt;supports-aptrack&gt;yes&lt;/supports-aptrack&gt;
				&lt;supports-delete&gt;yes&lt;/supports-delete&gt;
				&lt;published&gt;yes&lt;/published&gt;
				&lt;country&gt;GBR&lt;/country&gt;
			&lt;/portal&gt;
		&lt;/portals&gt;
		&lt;offset&gt;0&lt;/offset&gt;
		&lt;count&gt;5&lt;/count&gt;
		&lt;total&gt;11&lt;/total&gt;
	&lt;/response&gt;
	&lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>

In order to get the portal's logo image, append the value of its <logo> tag to the following path: http://www.idibu.com/images/stories/Portal_logos/
