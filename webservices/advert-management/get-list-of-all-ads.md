<p>Method returns all adverts for client, you can use both POST and GET methods</p>
<h1 class="p1">Parameters</h1>
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
				<p class="p2">from_date</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">date from where to return adverts, format: yyyy-mm-dd OR yyyy-mm-dd HH:MM:SS. By default date is not taken into account</p>
			</td>
		</tr>
		<tr>
			<td class="td1" valign="middle">
				<p class="p2">to_date</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">maximum advert date. Format: yyyy-mm-dd OR yyyy-mm-dd HH:MM:SS</p>
			</td>
		</tr>
		<tr>
			<td class="td1" valign="middle">
				<p class="p2">sender</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">numeric (sender id). filter adverts by sender. By default return adverts of all senders</p>
			</td>
		</tr>
		<tr>
			<td class="td1" valign="middle">
				<p class="p2">board</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">numeric (board id). filter adverts by board id</p>
			</td>
		</tr>
		<tr>
			<td class="td1" valign="middle">
				job-id</td>
			<td class="td2" valign="middle">
				No</td>
			<td class="td3" valign="middle">
				<p>numeric (job id). filter adverts by job id, multiple allowed, comma separated&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td class="td1" valign="middle">
				<p class="p2">reference</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">The reference of the job you wish to find records for</p>
			</td>
		</tr>
		<tr>
			<td class="td1" valign="middle">
				<p class="p2">title</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">The title of the job you wish to find records for</p>
			</td>
		</tr>
		<tr>
			<td class="td1" valign="middle">
				<p class="p2">title-or-reference</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">The title or reference of the job you wish to find records for</p>
			</td>
		</tr>
		<tr>
			<td class="td1" valign="middle">order</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">date-asc or date-desc options available</p>
			</td>
		</tr>
		<tr>
			<td class="td1" valign="middle">format</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
	<p class="p2">Possible values:<ul><li><code>count-jobs</code> - shows just the number of the jobs matching query criteria without any additional tags</li><li><code>details-live</code> - displays detailed info about each job's parameters</p>
			</td>
		</tr>
	</tbody>
</table>
<h1 class="p3">Example</h1>
<h2>Request</h2>
<pre><code>http://ws.idibu.com/ws/rest/v1/adverts/all/?hash=[your hash]&sender=529&offset=10&count=1&from_date=2011-09-14&to_date=2011-10-22</code></pre>
<h2>Response</h2>
<pre><code type="xml">
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
    &lt;response&gt;
        &lt;adverts&gt;
            &lt;advert&gt;
                &lt;id&gt;103971&lt;/id&gt;
                &lt;creation_date&gt;2011-11-07 17:53:28&lt;/creation_date&gt;
                &lt;expiry_date&gt;2011-12-07 00:00:01&lt;/expiry_date&gt;
                &lt;sender&gt;
                    &lt;id&gt;524&lt;/id&gt;
                    &lt;firstname&gt;Alice&lt;/firstname&gt;
                    &lt;lastname&gt;Wonderland&lt;/lastname&gt;
                    &lt;email&gt;mail@example.com&lt;/email&gt;
                &lt;/sender&gt;
                &lt;job&gt;
                    &lt;id&gt;33029844&lt;/id&gt;&lt;title&gt;&lt;/title&gt;
                    &lt;reference&gt;IJHW020897&lt;/reference&gt;
                &lt;/job&gt;
                &lt;aptrack&gt;
                    &lt;total&gt;0&lt;/total&gt;
                    &lt;unread&gt;0&lt;/unread&gt;
                &lt;/aptrack&gt;
                &lt;posting&gt;
                    &lt;success&gt;8&lt;/success&gt;
                    &lt;update&gt;0&lt;/update&gt;
                    &lt;fail&gt;0&lt;/fail&gt;
                    &lt;pending&gt;0&lt;/pending&gt;
                    &lt;delete&gt;0&lt;/delete&gt;
                &lt;/posting&gt;
            &lt;/advert&gt;
            &lt;advert&gt;
                &lt;id&gt;103875&lt;/id&gt;
                &lt;creation_date&gt;2011-11-07 12:09:01&lt;/creation_date&gt;
                &lt;expiry_date&gt;2011-12-05 00:00:01&lt;/expiry_date&gt;
                &lt;sender&gt;
                    &lt;id&gt;924&lt;/id&gt;
                    &lt;firstname&gt;Mayra&lt;/firstname&gt;
                    &lt;lastname&gt;Maxwell&lt;/lastname&gt;
                    &lt;email&gt;mail@example.com&lt;/email&gt;
                &lt;/sender&gt;
                &lt;job&gt;
                    &lt;id&gt;33029813&lt;/id&gt;&lt;title&gt;&lt;/title&gt;
                    &lt;reference&gt;HVCW020878&lt;/reference&gt;
                &lt;/job&gt;
                &lt;aptrack&gt;
                    &lt;total&gt;25&lt;/total&gt;
                    &lt;unread&gt;25&lt;/unread&gt;
                &lt;/aptrack&gt;
                &lt;posting&gt;
                    &lt;success&gt;6&lt;/success&gt;
                    &lt;update&gt;0&lt;/update&gt;
                    &lt;fail&gt;0&lt;/fail&gt;
                    &lt;pending&gt;0&lt;/pending&gt;
                    &lt;delete&gt;0&lt;/delete&gt;
                &lt;/posting&gt;
            &lt;/advert&gt;
            &lt;advert&gt;
                &lt;id&gt;103834&lt;/id&gt;
                &lt;creation_date&gt;2011-11-07 11:28:02&lt;/creation_date&gt;
                &lt;expiry_date&gt;2011-11-30 00:00:01&lt;/expiry_date&gt;
                &lt;sender&gt;
                    &lt;id&gt;470&lt;/id&gt;
                    &lt;firstname&gt;Calene&lt;/firstname&gt;
                    &lt;lastname&gt;Cibrock&lt;/lastname&gt;
                    &lt;email&gt;mail@example.com&lt;/email&gt;
                &lt;/sender&gt;
                &lt;job&gt;
                    &lt;id&gt;33029634&lt;/id&gt;&lt;title&gt;&lt;/title&gt;
                    &lt;reference&gt;CHYW020122&lt;/reference&gt;
                &lt;/job&gt;
                &lt;aptrack&gt;
                    &lt;total&gt;12&lt;/total&gt;
                    &lt;unread&gt;12&lt;/unread&gt;
                &lt;/aptrack&gt;
                &lt;posting&gt;
                    &lt;success&gt;0&lt;/success&gt;
                    &lt;update&gt;0&lt;/update&gt;
                    &lt;fail&gt;0&lt;/fail&gt;
                    &lt;pending&gt;0&lt;/pending&gt;
                    &lt;delete&gt;7&lt;/delete&gt;
                &lt;/posting&gt;
            &lt;/advert&gt;
            &lt;advert&gt;
                &lt;id&gt;103832&lt;/id&gt;
                &lt;creation_date&gt;2011-11-07 11:26:02&lt;/creation_date&gt;
                &lt;expiry_date&gt;2011-12-05 00:00:01&lt;/expiry_date&gt;
                &lt;sender&gt;
                    &lt;id&gt;563&lt;/id&gt;
                    &lt;firstname&gt;Ahanna&lt;/firstname&gt;
                    &lt;lastname&gt;Dask&lt;/lastname&gt;
                    &lt;email&gt;mail@example.com&lt;/email&gt;
                &lt;/sender&gt;
                &lt;job&gt;
                    &lt;id&gt;33029600&lt;/id&gt;&lt;title&gt;&lt;/title&gt;
                    &lt;reference&gt;JMSW020861&lt;/reference&gt;
                &lt;/job&gt;
                &lt;aptrack&gt;
                    &lt;total&gt;23&lt;/total&gt;
                    &lt;unread&gt;23&lt;/unread&gt;
                &lt;/aptrack&gt;
                &lt;posting&gt;
                    &lt;success&gt;6&lt;/success&gt;
                    &lt;update&gt;0&lt;/update&gt;
                    &lt;fail&gt;0&lt;/fail&gt;
                    &lt;pending&gt;0&lt;/pending&gt;
                    &lt;delete&gt;6&lt;/delete&gt;
                &lt;/posting&gt;
            &lt;/advert&gt;
            &lt;advert&gt;
                &lt;id&gt;103767&lt;/id&gt;
                &lt;creation_date&gt;2011-11-04 17:39:02&lt;/creation_date&gt;
                &lt;expiry_date&gt;2011-12-02 00:00:01&lt;/expiry_date&gt;
                &lt;sender&gt;
                    &lt;id&gt;1194&lt;/id&gt;
                    &lt;firstname&gt;Rebecca&lt;/firstname&gt;
                    &lt;lastname&gt;Grim&lt;/lastname&gt;
                    &lt;email&gt;mail@example.com&lt;/email&gt;
                &lt;/sender&gt;
                &lt;job&gt;
                    &lt;id&gt;33029799&lt;/id&gt;&lt;title&gt;&lt;/title&gt;
                    &lt;reference&gt;BEXW020895&lt;/reference&gt;
                &lt;/job&gt;
                &lt;aptrack&gt;
                    &lt;total&gt;26&lt;/total&gt;
                    &lt;unread&gt;26&lt;/unread&gt;
                &lt;/aptrack&gt;
                &lt;posting&gt;
                    &lt;success&gt;7&lt;/success&gt;
                    &lt;update&gt;0&lt;/update&gt;
                    &lt;fail&gt;0&lt;/fail&gt;
                    &lt;pending&gt;0&lt;/pending&gt;
                    &lt;delete&gt;0&lt;/delete&gt;
                &lt;/posting&gt;
            &lt;/advert&gt;
            &lt;advert&gt;
                &lt;id&gt;103764&lt;/id&gt;
                &lt;creation_date&gt;2011-11-04 17:34:19&lt;/creation_date&gt;
                &lt;expiry_date&gt;2011-12-02 00:00:01&lt;/expiry_date&gt;
                &lt;sender&gt;
                    &lt;id&gt;1194&lt;/id&gt;
                    &lt;firstname&gt;Rebecca&lt;/firstname&gt;
                    &lt;lastname&gt;Grim&lt;/lastname&gt;
                    &lt;email&gt;mail@example.com&lt;/email&gt;
                &lt;/sender&gt;
                &lt;job&gt;
                    &lt;id&gt;33029798&lt;/id&gt;&lt;title&gt;&lt;/title&gt;
                    &lt;reference&gt;BEXW020894&lt;/reference&gt;
                &lt;/job&gt;
                &lt;aptrack&gt;
                    &lt;total&gt;62&lt;/total&gt;
                    &lt;unread&gt;62&lt;/unread&gt;
                &lt;/aptrack&gt;
                &lt;posting&gt;
                    &lt;success&gt;7&lt;/success&gt;
                    &lt;update&gt;0&lt;/update&gt;
                    &lt;fail&gt;0&lt;/fail&gt;
                    &lt;pending&gt;0&lt;/pending&gt;
                    &lt;delete&gt;0&lt;/delete&gt;
                &lt;/posting&gt;
            &lt;/advert&gt;
            &lt;advert&gt;
                &lt;id&gt;103742&lt;/id&gt;
                &lt;creation_date&gt;2011-11-04 16:36:30&lt;/creation_date&gt;
                &lt;expiry_date&gt;2011-12-02 00:00:01&lt;/expiry_date&gt;
                &lt;sender&gt;
                    &lt;id&gt;468&lt;/id&gt;
                    &lt;firstname&gt;Errinaya &lt;/firstname&gt;
                    &lt;lastname&gt;Badek&lt;/lastname&gt;
                    &lt;email&gt;mail@example.com&lt;/email&gt;
                &lt;/sender&gt;
                &lt;job&gt;
                    &lt;id&gt;33029794&lt;/id&gt;&lt;title&gt;&lt;/title&gt;
                    &lt;reference&gt;MCDW020742&lt;/reference&gt;
                &lt;/job&gt;
                &lt;aptrack&gt;
                    &lt;total&gt;6&lt;/total&gt;
                    &lt;unread&gt;6&lt;/unread&gt;
                &lt;/aptrack&gt;
                &lt;posting&gt;
                    &lt;success&gt;6&lt;/success&gt;
                    &lt;update&gt;0&lt;/update&gt;
                    &lt;fail&gt;1&lt;/fail&gt;
                    &lt;pending&gt;0&lt;/pending&gt;
                    &lt;delete&gt;0&lt;/delete&gt;
                &lt;/posting&gt;
            &lt;/advert&gt;
            &lt;advert&gt;
                &lt;id&gt;103739&lt;/id&gt;
                &lt;creation_date&gt;2011-11-04 16:33:09&lt;/creation_date&gt;
                &lt;expiry_date&gt;2011-11-25 00:00:01&lt;/expiry_date&gt;
                &lt;sender&gt;
                    &lt;id&gt;468&lt;/id&gt;
                    &lt;firstname&gt;Errinaya &lt;/firstname&gt;
                    &lt;lastname&gt;Badek&lt;/lastname&gt;
                    &lt;email&gt;mail@example.com&lt;/email&gt;
                &lt;/sender&gt;
                &lt;job&gt;
                    &lt;id&gt;33029519&lt;/id&gt;&lt;title&gt;&lt;/title&gt;
                    &lt;reference&gt;MCDW020742&lt;/reference&gt;
                &lt;/job&gt;
                &lt;aptrack&gt;
                    &lt;total&gt;12&lt;/total&gt;
                    &lt;unread&gt;12&lt;/unread&gt;
                &lt;/aptrack&gt;
                &lt;posting&gt;
                    &lt;success&gt;0&lt;/success&gt;
                    &lt;update&gt;0&lt;/update&gt;
                    &lt;fail&gt;0&lt;/fail&gt;
                    &lt;pending&gt;0&lt;/pending&gt;
                    &lt;delete&gt;7&lt;/delete&gt;
                &lt;/posting&gt;
            &lt;/advert&gt;
            &lt;advert&gt;
                &lt;id&gt;103738&lt;/id&gt;
                &lt;creation_date&gt;2011-11-04 16:32:22&lt;/creation_date&gt;
                &lt;expiry_date&gt;2011-12-02 00:00:01&lt;/expiry_date&gt;
                &lt;sender&gt;
                    &lt;id&gt;468&lt;/id&gt;
                    &lt;firstname&gt;Errinaya &lt;/firstname&gt;
                    &lt;lastname&gt;Badek&lt;/lastname&gt;
                    &lt;email&gt;mail@example.com&lt;/email&gt;
                &lt;/sender&gt;
                &lt;job&gt;
                    &lt;id&gt;33029793&lt;/id&gt;&lt;title&gt;&lt;/title&gt;
                    &lt;reference&gt;MCDW020787&lt;/reference&gt;
                &lt;/job&gt;
                &lt;aptrack&gt;
                    &lt;total&gt;8&lt;/total&gt;
                    &lt;unread&gt;8&lt;/unread&gt;
                &lt;/aptrack&gt;
                &lt;posting&gt;
                    &lt;success&gt;6&lt;/success&gt;
                    &lt;update&gt;0&lt;/update&gt;
                    &lt;fail&gt;1&lt;/fail&gt;
                    &lt;pending&gt;0&lt;/pending&gt;
                    &lt;delete&gt;0&lt;/delete&gt;
                &lt;/posting&gt;
            &lt;/advert&gt;
            &lt;advert&gt;
                &lt;id&gt;103734&lt;/id&gt;
                &lt;creation_date&gt;2011-11-04 16:31:01&lt;/creation_date&gt;
                &lt;expiry_date&gt;2011-11-25 00:00:01&lt;/expiry_date&gt;
                &lt;sender&gt;
                    &lt;id&gt;468&lt;/id&gt;
                    &lt;firstname&gt;Errinaya &lt;/firstname&gt;
                    &lt;lastname&gt;Badek&lt;/lastname&gt;
                    &lt;email&gt;mail@example.com&lt;/email&gt;
                &lt;/sender&gt;
                &lt;job&gt;
                    &lt;id&gt;33029521&lt;/id&gt;&lt;title&gt;&lt;/title&gt;
                    &lt;reference&gt;MCDW020787&lt;/reference&gt;
                &lt;/job&gt;
                &lt;aptrack&gt;
                    &lt;total&gt;8&lt;/total&gt;
                    &lt;unread&gt;8&lt;/unread&gt;
                &lt;/aptrack&gt;
                &lt;posting&gt;
                    &lt;success&gt;0&lt;/success&gt;
                    &lt;update&gt;0&lt;/update&gt;
                    &lt;fail&gt;0&lt;/fail&gt;
                    &lt;pending&gt;0&lt;/pending&gt;
                    &lt;delete&gt;7&lt;/delete&gt;
                &lt;/posting&gt;
            &lt;/advert&gt;
        &lt;/adverts&gt;
        &lt;total&gt;1590&lt;/total&gt;
    &lt;/response&gt;
    &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
