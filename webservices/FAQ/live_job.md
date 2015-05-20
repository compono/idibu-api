<h1>How to check if speciic job is live?</h1>
<br>
To check whether a specific job is live (as in live on any board previously posted to), you have to determine any advert_id of the job reference you have posted previously. To begin you need to call the <a href="https://github.com/oneworldmarket/idibu-api/blob/master/webservices/advert-management/get-list-of-all-ads.md" target ="_blank"> all adverts webservice </a> with specific job reference:

<pre>
<code>
http://ws.idibu.com/ws/rest/v1/adverts/all/?hash=(your hash)&reference=(reference you wish to check)
</code></pre>

Say we want to check for reference "idibu_ws"

<pre>
<code>
http://ws.idibu.com/ws/rest/v1/adverts/all/?hash=ThisIsAfakeHash123&reference=idibu_ws
</code></pre>

<h2>
	Response</h2>
<pre>
<code>
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
&lt;response&gt;
&lt;adverts&gt;
<b><u>&lt;advert&gt;
	&lt;id&gt;3336727&lt;/id&gt;</b></u>
	&lt;delete_log&gt;0&lt;/delete_log&gt;
	&lt;creation_date&gt;2015-05-20 12:11:04&lt;/creation_date&gt;
	&lt;expiry_date&gt;0000-00-00 00:00:00&lt;/expiry_date&gt;
	&lt;sender&gt;
		&lt;id&gt;3005974&lt;/id&gt;
		&lt;firstname&gt;Dalek&lt;/firstname&gt;
		&lt;lastname&gt;Khan&lt;/lastname&gt;
		&lt;email&gt;khan@idibu.com&lt;/email&gt;
	&lt;/sender&gt;
	&lt;job&gt;
		&lt;id&gt;37086033&lt;/id&gt;
		&lt;title&gt;WS testing&lt;/title&gt;
		&lt;reference&gt;idibu_ws&lt;/reference&gt;
	&lt;/job&gt;
	&lt;aptrack&gt;
		&lt;total&gt;0&lt;/total&gt;
		&lt;unread&gt;0&lt;/unread&gt;
	&lt;/aptrack&gt;
	&lt;posting&gt;
		&lt;success&gt;2&lt;/success&gt;
		&lt;update&gt;0&lt;/update&gt;
		&lt;fail&gt;1&lt;/fail&gt;
		&lt;pending&gt;0&lt;/pending&gt;
		&lt;delete&gt;0&lt;/delete&gt;
	&lt;/posting&gt;
	&lt;/advert&gt;
&lt;/adverts&gt;
&lt;total&gt;1&lt;/total&gt;
&lt;/response&gt;
&lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>

The number you need is the bolded in the XML below. Once you obtain this number, you can use the <a href="https://github.com/oneworldmarket/idibu-api/blob/master/webservices/advert-management/get-individual-ad-details.md" target="_blank">individual ad details ws</a> with the "live" format to see what is the live status of your job reference.

<pre>
<code>
http://ws.idibu.com/ws/rest/v1/adverts/(advert id)/?hash=ThisIsAfakeHash123&format=live
</code></pre>

so for the advert id seen above:

<pre>
<code>
http://ws.idibu.com/ws/rest/v1/adverts/3336727/?hash=(your hash)&format=live
</code></pre>

<h2>
	Response</h2>
<pre>
<code>
&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot;?&gt;
&lt;idibu version=&quot;1.0&quot; generator=&quot;idibu&quot;&gt;
	&lt;response&gt;
	&lt;advert&gt;
		&lt;id&gt;3336727&lt;/id&gt;
		&lt;delete_log&gt;0&lt;/delete_log&gt;
		&lt;creation_date&gt;2015-05-20 12:11:04&lt;/creation_date&gt;
		&lt;expiry_date&gt;0000-00-00 00:00:00&lt;/expiry_date&gt;
		&lt;sender&gt;
			&lt;id&gt;3005974&lt;/id&gt;
			&lt;firstname&gt;Dalek&lt;/firstname&gt;
			&lt;lastname&gt;Khan&lt;/lastname&gt;
			&lt;email&gt;khan@idibu.com&lt;/email&gt;
		&lt;/sender&gt;
		&lt;job&gt;
			&lt;id&gt;37086033&lt;/id&gt;
			&lt;title&gt;WS testing&lt;/title&gt;
			&lt;reference&gt;idibu_ws&lt;/reference&gt;
			&lt;description&gt;this is a testing role, please ignore.&lt;/description&gt;
			&lt;sector id=&quot;1&quot;&gt;Accountancy&lt;/sector&gt;
			&lt;location id=&quot;GB&quot;&gt;United Kingdom&lt;/location&gt;
			&lt;sub_location id=&quot;1009482&quot;&gt;Testwood&lt;/sub_location&gt;
			&lt;type id=&quot;2&quot;&gt;Permanent&lt;/type&gt;
			&lt;duration&gt;n/a&lt;/duration&gt;
			&lt;salary_minimum&gt;456&lt;/salary_minimum&gt;
			&lt;salary_maximum&gt;656&lt;/salary_maximum&gt;
			&lt;salary_per&gt;annum&lt;/salary_per&gt;
			&lt;salary_currency&gt;GBP&lt;/salary_currency&gt;
			&lt;salary_extras/&gt;
			&lt;salary_override/&gt;
			&lt;application_url/&gt;
			&lt;start_date&gt;2015-05-20 00:00:00&lt;/start_date&gt;
		&lt;/job&gt;
		&lt;aptrack&gt;
			&lt;total&gt;0&lt;/total&gt;
			&lt;unread&gt;0&lt;/unread&gt;
		&lt;/aptrack&gt;
		&lt;posting&gt;
	<b>		&lt;live&gt;2&lt;/live&gt; </b>
			&lt;live_failed&gt;0&lt;/live_failed&gt;
			&lt;failed&gt;1&lt;/failed&gt;
			&lt;deleted&gt;0&lt;/deleted&gt;
			&lt;deleted_failed&gt;0&lt;/deleted_failed&gt;
			&lt;expired&gt;0&lt;/expired&gt;
			&lt;expired_failed&gt;0&lt;/expired_failed&gt;
			&lt;updated&gt;0&lt;/updated&gt;
			&lt;updated_failed&gt;0&lt;/updated_failed&gt;
			&lt;pending&gt;0&lt;/pending&gt;
				&lt;details&gt;
					&lt;detail&gt;
						&lt;portal&gt;
						&lt;id&gt;253&lt;/id&gt;
						&lt;url&gt;www.freespace.com&lt;/url&gt;
						&lt;logo&gt;monstertest2014.png&lt;/logo&gt;
						&lt;name&gt;Monster Test&lt;/name&gt;
						&lt;/portal&gt;
						&lt;post&gt;
						&lt;start&gt;2015-05-20 12:11:04&lt;/start&gt;
						&lt;stop&gt;2015-06-19 00:00:01&lt;/stop&gt;
						&lt;status&gt;live&lt;/status&gt;
						&lt;deletable&gt;yes&lt;/deletable&gt;
						&lt;/post&gt;
						&lt;applicants/&gt;
						&lt;link&gt;http://jobview.monster.co.uk/UK-150965156.aspx&lt;/link&gt;
					&lt;/detail&gt;
					&lt;detail&gt;
						&lt;portal&gt;
						&lt;id&gt;1229&lt;/id&gt;
						&lt;url&gt;www.idibu.com&lt;/url&gt;
						&lt;logo&gt;idibunew.jpg&lt;/logo&gt;
						&lt;name&gt;idibu CV manager&lt;/name&gt;
						&lt;/portal&gt;
						&lt;post&gt;
						&lt;start&gt;2015-05-20 12:11:07&lt;/start&gt;
						&lt;stop&gt;0000-00-00 00:00:00&lt;/stop&gt;
						&lt;status&gt;live&lt;/status&gt;
						&lt;deletable&gt;no&lt;/deletable&gt;
						&lt;/post&gt;
						&lt;applicants/&gt;
						&lt;link&gt;dalek.k.a4liybmypar@idibu.aptrack.co.uk&lt;/link&gt;
						&lt;/detail&gt;
					&lt;detail&gt;
						&lt;portal&gt;
						&lt;id&gt;118&lt;/id&gt;
						&lt;url&gt;freespace.com&lt;/url&gt;
						&lt;logo&gt;idibu.jpg&lt;/logo&gt;
						&lt;name&gt;zzzzNew search board test&lt;/name&gt;
						&lt;/portal&gt;
						&lt;post&gt;
						&lt;start&gt;2015-05-20 12:11:09&lt;/start&gt;
						&lt;stop&gt;2015-05-21 00:00:01&lt;/stop&gt;
						&lt;status&gt;failed&lt;/status&gt;
						&lt;deletable&gt;no&lt;/deletable&gt;
						&lt;errordetails&gt;
							&lt;errordetail&gt;
								&lt;description&gt;An unknown error has occurred.&lt;/description&gt;
								&lt;reasons&gt;- Could be something simple like incorrect username and password - please check your creds with your Account Manager.&lt;br/&gt;- Could be that the account is out of credits with the board. Again, check with your Account Manager.&lt;br/&gt;- As it&#39;s an unknown error, it could be one of many things. Best to report it to support@idibu.com and we&#39;ll take a look.&lt;/reasons&gt;
							&lt;/errordetail&gt;
						&lt;/errordetails&gt;
						&lt;/post&gt;
						&lt;applicants/&gt;
						&lt;link/&gt;
					&lt;/detail&gt;
				&lt;/details&gt;
			&lt;/posting&gt;
		&lt;/advert&gt;
	&lt;/response&gt;
&lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>

The bolded "live" tag will show you on how many portals is the job live on. If it's more then 0, then the job is stil live. The tags below will show you the status of each post on every portal the job was posted to.
