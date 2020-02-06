<p>idibu can be set to send addititional metadata within the header of applicant emails which you can use to parse additional data back into your own database for your own tracking and reporting purposes.</p>
<p>An example of this is:</p>
<pre>
<code>
X-iTrackID: 40809163
X-iTrackID-PortalID: 338
X-iTrackID-Portal-Name: Seek
X-iTrackID-ClientSettingsID: 3007241
X-iTrackID-ClientSettings-Name: Kara Smith (karas@idibu.com)
X-iTrackID-Office: New Zealand
X-iTrackID-Team: AUK JS Uploads
X-iTrackID-PostLogID: 38504886
X-iTrackID-JobID: 37068825
X-iTrackID-Title: Senior .Net Developer
X-iTrackID-Reference: JO-1502-428583
X-iTrackID-Type: 2 Permanent
</code></pre>
<p>where the data types are:</p>
<ul>
	<li>
		X-iTrackID-ClientReference: Unique external (customer) reference for this job (<a href="https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/jobidvsjobref.md">Details on this are here</a>)</li>
	<li>
		X-iTrackID: Unique internal idibu reference for this applicant</li>
	<li>
		X-iTrackID-Portalid: Unique internal idibu job board id</li>
	<li>
		X-iTrackID-Portal-Name: Name of the Job Board or other applicant source</li>
	<li>
		X-iTrackID-Clientsettingsid: Internal idibu reference of person who posted the advert</li>
	<li>
		X-iTrackID-Clientsettings-Name: Name and email of the advert sender</li>
	<li>
		X-iTrackID-Office: Name the advert sender's office</li>
	<li>
		X-iTrackID-Team: Name of the advert sender's team</li>
	<li>
		X-iTrackID-Postlogid: Unique internal idibu posting reference for this applicant</li>
	<li>
		X-iTrackID-Jobid: Unique internal idibu posting reference for this applicant</li>
	<li>
		X-iTrackID-Title: Advert job title</li>
	<li>
		X-iTrackID-Reference: Advert job reference</li>
	<li>
		X-iTrackID-Type: Job type, i.e. Permanent, Contract etc</li>
</ul>
<p>The subject of the email can also be customised if you would like tracking added there as well.</p>
