<p>Method returns detailed advert information for given advert id</p>
<h1>
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
				<p class="p2"><b>live</b> is the only possible value; it displays job details instead of describing status of each post. Rather than seeing all the reposting entries for one particular board, you will only be informed if the job is live, expired, deleted or has errored in any way. This can be used to show ad status for external/partner job interface rather than whole posting history, which displays without this parameter.</p>
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
http://ws.idibu.com/ws/rest/v1/adverts/123?hash=<your hash>
</code></pre>
<h2>
	Response</h2>
<pre>
&lt;code type=&quot;xml&quot;&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
    &lt;response&gt;
        &lt;advert&gt;
            &lt;id&gt;103742&lt;/id&gt;
            &lt;creation_date&gt;2011-11-04 16:36:30&lt;/creation_date&gt;
            &lt;expiry_date&gt;2011-12-02 00:00:01&lt;/expiry_date&gt;
            &lt;sender&gt;
                &lt;id&gt;468&lt;/id&gt;
                &lt;firstname&gt;Alice&lt;/firstname&gt;
                &lt;lastname&gt;Wonderland&lt;/lastname&gt;
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
                &lt;success&gt;5&lt;/success&gt;
                &lt;update&gt;0&lt;/update&gt;
                &lt;fail&gt;1&lt;/fail&gt;
                &lt;pending&gt;0&lt;/pending&gt;
                &lt;delete&gt;0&lt;/delete&gt;&lt;details&gt;
                    &lt;detail&gt;
                        &lt;portal&gt;
                            &lt;id&gt;15&lt;/id&gt;
                            &lt;url&gt;www.totaljobs.com&lt;/url&gt;
                            &lt;logo&gt;totaljobs2.jpg&lt;/logo&gt;
                            &lt;name&gt;Total Jobs&lt;/name&gt;
                        &lt;/portal&gt;
                        &lt;post&gt;
                            &lt;start&gt;2011-11-04 16:39:09&lt;/start&gt;
                            &lt;stop&gt;2011-12-02 00:00:01&lt;/stop&gt;
                            &lt;type&gt;post&lt;/type&gt;
                            &lt;status&gt;success&lt;/status&gt;
                        &lt;/post&gt;
                        &lt;expired&gt;no&lt;/expired&gt;
                        &lt;applicants&gt;3&lt;/applicants&gt;&lt;link /&gt;http://www.totaljobs.com/JobSearch/JobDetails.aspx?JobID=12345678
                    &lt;/detail&gt;
                    &lt;detail&gt;
                        &lt;portal&gt;
                            &lt;id&gt;925&lt;/id&gt;
                            &lt;url&gt;www.jobs.co.uk&lt;/url&gt;
                            &lt;logo&gt;jobscouk.jpg&lt;/logo&gt;
                            &lt;name&gt;Jobs.co.uk&lt;/name&gt;
                        &lt;/portal&gt;
                        &lt;post&gt;
                            &lt;start&gt;2011-11-04 16:37:42&lt;/start&gt;
                            &lt;stop&gt;2011-12-02 00:00:01&lt;/stop&gt;
                            &lt;type&gt;post&lt;/type&gt;
                            &lt;status&gt;success&lt;/status&gt;
                        &lt;/post&gt;
                        &lt;expired&gt;no&lt;/expired&gt;
                        &lt;applicants&gt;0&lt;/applicants&gt;&lt;link /&gt;
                    &lt;/detail&gt;
                    &lt;detail&gt;
                        &lt;portal&gt;
                            &lt;id&gt;205&lt;/id&gt;
                            &lt;url&gt;www.personneltoday.com&lt;/url&gt;
                            &lt;logo&gt;perstoday2.jpg&lt;/logo&gt;
                            &lt;name&gt;Personnel Today&lt;/name&gt;
                        &lt;/portal&gt;
                        &lt;post&gt;
                            &lt;start&gt;2011-11-04 16:37:33&lt;/start&gt;
                            &lt;stop&gt;2011-12-02 00:00:01&lt;/stop&gt;
                            &lt;type&gt;post&lt;/type&gt;
                            &lt;status&gt;success&lt;/status&gt;
                        &lt;/post&gt;
                        &lt;expired&gt;no&lt;/expired&gt;
                        &lt;applicants&gt;1&lt;/applicants&gt;&lt;link /&gt;http://www.personneltoday.com/jobs/job/xyz-123456789.htm
                    &lt;/detail&gt;
                    &lt;detail&gt;
                        &lt;portal&gt;
                            &lt;id&gt;549&lt;/id&gt;
                            &lt;url&gt;www.changeboard.com&lt;/url&gt;
                            &lt;logo&gt;changebu.jpg&lt;/logo&gt;
                            &lt;name&gt;ChangeBoard&lt;/name&gt;
                        &lt;/portal&gt;
                        &lt;post&gt;
                            &lt;start&gt;2011-11-04 16:36:44&lt;/start&gt;
                            &lt;stop&gt;2011-12-02 00:00:01&lt;/stop&gt;
                            &lt;type&gt;post&lt;/type&gt;
                            &lt;status&gt;success&lt;/status&gt;
                        &lt;/post&gt;
                        &lt;expired&gt;no&lt;/expired&gt;
                        &lt;applicants&gt;1&lt;/applicants&gt;&lt;link /&gt;http://www.changeboard.com/jobs/details/123456/
                    &lt;/detail&gt;
                    &lt;detail&gt;
                        &lt;portal&gt;
                            &lt;id&gt;618&lt;/id&gt;
                            &lt;url&gt;www.peoplemanagement.co.uk&lt;/url&gt;
                            &lt;logo&gt;peoplemanagment.jpg&lt;/logo&gt;
                            &lt;name&gt;People Management&lt;/name&gt;
                        &lt;/portal&gt;
                        &lt;post&gt;
                            &lt;start&gt;2011-11-04 16:36:30&lt;/start&gt;
                            &lt;stop&gt;2011-12-02 00:00:01&lt;/stop&gt;
                            &lt;type&gt;post&lt;/type&gt;
                            &lt;status&gt;success&lt;/status&gt;
                        &lt;/post&gt;
                        &lt;expired&gt;no&lt;/expired&gt;
                        &lt;applicants&gt;1&lt;/applicants&gt;&lt;link /&gt;
                    &lt;/detail&gt;
                    &lt;detail&gt;
                        &lt;portal&gt;
                            &lt;id&gt;155&lt;/id&gt;
                            &lt;url&gt;www.simplyhrjobs.co.uk&lt;/url&gt;
                            &lt;logo&gt;simplyhr.jpg&lt;/logo&gt;
                            &lt;name&gt;Simply HR Jobs&lt;/name&gt;
                        &lt;/portal&gt;
                        &lt;post&gt;
                            &lt;start&gt;2011-11-04 16:36:30&lt;/start&gt;
                            &lt;stop&gt;2011-12-02 00:00:01&lt;/stop&gt;
                            &lt;type&gt;post&lt;/type&gt;
                            &lt;status&gt;fail&lt;/status&gt;
                        &lt;/post&gt;
                        &lt;expired&gt;no&lt;/expired&gt;
                        &lt;applicants&gt;0&lt;/applicants&gt;&lt;link /&gt;
                    &lt;/detail&gt;&lt;/details&gt;
            &lt;/posting&gt;
        &lt;/advert&gt;
    &lt;/response&gt;
    &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
<h1>
	Example</h1>
<h2>
	Request</h2>
<pre>
<code>
http://ws.idibu.com/ws/rest/v1/adverts/123?hash=<your hash>&format=live
</code></pre>
<h2>
	Response</h2>
<pre>
<code type="xml">
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
&lt;response&gt;
&lt;advert&gt;
	&lt;id&gt;844&lt;/id&gt;
	&lt;creation_date&gt;2011-11-28 09:17:41&lt;/creation_date&gt;
	&lt;expiry_date&gt;0000-00-00 00:00:00&lt;/expiry_date&gt;
	&lt;sender&gt;
	&lt;id&gt;16&lt;/id&gt;
		&lt;firstname&gt;Dalek&lt;/firstname&gt;
		&lt;lastname&gt;1&lt;/lastname&gt;
		&lt;email&gt;hush@stay.put&lt;/email&gt;
	&lt;/sender&gt;
	&lt;job&gt;
		&lt;id&gt;35000232&lt;/id&gt;&lt;title&gt;&lt;/title&gt;
		&lt;reference&gt;char tesr&lt;/reference&gt;
		&lt;description&gt;&amp;pound; &lt;strong&gt;Basic Te&lt;/strong&gt; &amp;pound; $ &amp;amp; % @ &amp;amp; ! ? .,=)(/ -:;_+ &amp;#39; &amp;quot; &amp;#39; &amp;euro; &amp;pound; &lt;span style=&quot;text-decoration: underline;&quot;&gt;Basic Te&lt;/span&gt; &amp;pound; $ &amp;amp; % @ &amp;amp; ! ? .,=)(/ -:;_+ &amp;#39; &amp;quot; &amp;#39; &amp;euro; &amp;pound; &lt;em&gt;Basic Te&lt;/em&gt; &amp;pound; $ &amp;amp; % @ &amp;amp; ! ? .,=)(/ -:;_+ &amp;#39; &amp;quot; &amp;#39; &amp;euro; &amp;pound;
		&lt;/description&gt;
		&lt;sector&gt;Accountancy&lt;/sector&gt;
		&lt;location&gt;United Kingdom&lt;/location&gt;
		&lt;sub_location&gt;Lonbain&lt;/sub_location&gt;
		&lt;type&gt;Contract&lt;/type&gt;
		&lt;salary_minimum&gt;1&lt;/salary_minimum&gt;
		&lt;salary_maximum&gt;231&lt;/salary_maximum&gt;
		&lt;salary_per&gt;annum&lt;/salary_per&gt;
		&lt;salary_currency&gt;GBP&lt;/salary_currency&gt;
		&lt;salary_extras&gt;
		&lt;start_date&gt;2012-09-28 00:00:00&lt;/start_date&gt;
	&lt;/salary_extras&gt;&lt;/job&gt;
	&lt;aptrack&gt;
		&lt;total&gt;0&lt;/total&gt;
		&lt;unread&gt;0&lt;/unread&gt;
	&lt;/aptrack&gt;
	&lt;posting&gt;
		&lt;live&gt;0&lt;/live&gt;
		&lt;live_error&gt;0&lt;/live_error&gt;
		&lt;error&gt;0&lt;/error&gt;
		&lt;deleted&gt;1&lt;/deleted&gt;
		&lt;deleted_error&gt;0&lt;/deleted_error&gt;
		&lt;expired&gt;0&lt;/expired&gt;
		&lt;expired_error&gt;0&lt;/expired_error&gt;
		&lt;updated&gt;0&lt;/updated&gt;
		&lt;updated_error&gt;0&lt;/updated_error&gt;
		&lt;pending&gt;0&lt;/pending&gt;&lt;details&gt;
			&lt;detail&gt;
				&lt;portal&gt;
					&lt;id&gt;1195&lt;/id&gt;
					&lt;url&gt;www.idibu.com&lt;/url&gt;
					&lt;logo&gt;idibu.jpg&lt;/logo&gt;
					&lt;name&gt;Idibu dev board&lt;/name&gt;
				&lt;/portal&gt;
				&lt;post&gt;
					&lt;start&gt;2011-11-28 09:21:13&lt;/start&gt;
					&lt;stop&gt;0000-00-00 00:00:00&lt;/stop&gt;
					&lt;status&gt;deleted&lt;/status&gt;
					&lt;deletable&gt;no&lt;/deletable&gt;
				&lt;/post&gt;
				&lt;applicants&gt;0&lt;/applicants&gt;&lt;link /&gt;
			&lt;/detail&gt;&lt;/details&gt;&lt;link /&gt;
	&lt;/posting&gt;&lt;link /&gt;
&lt;/advert&gt;&lt;link /&gt;
&lt;/response&gt;&lt;link /&gt;
&lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
