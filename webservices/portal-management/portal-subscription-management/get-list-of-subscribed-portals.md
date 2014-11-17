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
				<p class="p2">filter portals by tags</p>
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
http://ws.idibu.com/ws/rest/v1/portals/subscribed?hash=<your hash>&count=100&filter_name=defence
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
                &lt;id&gt;918&lt;/id&gt;
                &lt;name&gt;3wJobs&lt;/name&gt;
                &lt;url&gt;www.3wjobs.co.uk&lt;/url&gt;
                &lt;logo&gt;3wjobs.jpg&lt;/logo&gt;
                &lt;tags&gt;general,free,&lt;/tags&gt;
            &lt;/portal&gt;
            &lt;portal&gt;
                &lt;id&gt;18&lt;/id&gt;
                &lt;name&gt;4 Recruitment Jobs&lt;/name&gt;
                &lt;url&gt;www.4recruitmentjobs.com&lt;/url&gt;
                &lt;logo&gt;4recr.jpg&lt;/logo&gt;
                &lt;tags&gt;general,free,&lt;/tags&gt;
            &lt;/portal&gt;
            &lt;portal&gt;
                &lt;id&gt;448&lt;/id&gt;
                &lt;name&gt;4 UK Jobs&lt;/name&gt;
                &lt;url&gt;www.4ukjobs.net&lt;/url&gt;
                &lt;logo&gt;4uk.jpg&lt;/logo&gt;
                &lt;tags&gt;general,free,&lt;/tags&gt;
            &lt;/portal&gt;
            &lt;portal&gt;
                &lt;id&gt;39&lt;/id&gt;
                &lt;name&gt;CV - Library&lt;/name&gt;
                &lt;url&gt;www.cv-library.co.uk&lt;/url&gt;
                &lt;logo&gt;cvlibrarylogo_ibidu.gif&lt;/logo&gt;
                &lt;tags&gt;general,all,&lt;/tags&gt;
            &lt;/portal&gt;
            &lt;portal&gt;
                &lt;id&gt;517&lt;/id&gt;
                &lt;name&gt;idibu Developer Board&lt;/name&gt;
                &lt;url&gt;jobboardtest.idibu.com&lt;/url&gt;
                &lt;logo&gt;idibu.jpg&lt;/logo&gt;
                &lt;tags&gt;&lt;/tags&gt;
            &lt;/portal&gt;
            &lt;portal&gt;
                &lt;id&gt;86&lt;/id&gt;
                &lt;name&gt;Monster UK&lt;/name&gt;
                &lt;url&gt;www.monster.co.uk&lt;/url&gt;
                &lt;logo&gt;monster2.jpg&lt;/logo&gt;
                &lt;tags&gt;general,all,&lt;/tags&gt;
            &lt;/portal&gt;
            &lt;portal&gt;
                &lt;id&gt;146&lt;/id&gt;
                &lt;name&gt;Oil and Gas Job Search&lt;/name&gt;
                &lt;url&gt;www.oilandgasjobsearch.com&lt;/url&gt;
                &lt;logo&gt;newoilandgas.jpg&lt;/logo&gt;
                &lt;tags&gt;engineering,utilities,&lt;/tags&gt;
            &lt;/portal&gt;
            &lt;portal&gt;
                &lt;id&gt;65&lt;/id&gt;
                &lt;name&gt;Oil Careers&lt;/name&gt;
                &lt;url&gt;www.oilcareers.com&lt;/url&gt;
                &lt;logo&gt;oilcar2.jpg&lt;/logo&gt;
                &lt;tags&gt;engineering,&lt;/tags&gt;
            &lt;/portal&gt;
            &lt;portal&gt;
                &lt;id&gt;560&lt;/id&gt;
                &lt;name&gt;STV jobs&lt;/name&gt;
                &lt;url&gt;www.jobs.stv.tv&lt;/url&gt;
                &lt;logo&gt;stvj.jpg&lt;/logo&gt;
                &lt;tags&gt;regional,&lt;/tags&gt;
            &lt;/portal&gt;
        &lt;/portals&gt;
        &lt;offset&gt;0&lt;/offset&gt;
        &lt;count&gt;9&lt;/count&gt;
        &lt;total&gt;9&lt;/total&gt;
    &lt;/response&gt;
    &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
