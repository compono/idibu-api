<p>idibu can be set to send addititional metadata within the header of applicant emails which you can use to parse additional data back into your own database for your own tracking and reporting purposes.</p>
<p>An example of this is:</p>
<pre>
<code>
X-Itrackid-ClientReference: Some-CUSTOM-Ref
X-Itrackid: 33139609
X-Itrackid-Portalid: 517
X-Itrackid-Portal-Name: idibu Developer Board
X-Itrackid-Clientsettingsid: 602
X-Itrackid-Clientsettings-Name: Steve Walker (steve@idibu.com)
X-Itrackid-Postlogid: 333064639
X-Itrackid-Jobid: 33007724
X-Itrackid-Title: Financial Services Roles
X-Itrackid-Reference: testref123
X-Itrackid-Type: 2 Permanent
</code></pre>
<p>where the data types are:</p>
<ul>
	<li>
		X-Itrackid-ClientReference: Unique external (customer) reference for this job (<a href="/docs/job-id-vs-client-ref">Details on this are here</a>)</li>
	<li>
		X-Itrackid: Unique internal idibu reference for this applicant</li>
	<li>
		X-Itrackid-Portalid: Unique internal idibu job board id</li>
	<li>
		X-Itrackid-Portal-Name: Name of the Job Board or other applicant source</li>
	<li>
		X-Itrackid-Clientsettingsid: Internal idibu reference of person who posted the advert</li>
	<li>
		X-Itrackid-Clientsettings-Name: Name and email of the advert sender</li>
	<li>
		X-Itrackid-Postlogid: Unique internal idibu posting reference for this applicant</li>
	<li>
		X-Itrackid-Jobid: Unique internal idibu posting reference for this applicant</li>
	<li>
		X-Itrackid-Title: Advert job title</li>
	<li>
		X-Itrackid-Reference: Advert job reference</li>
	<li>
		X-Itrackid-Type: Job type, i.e. Permanent, Contract etc</li>
</ul>
<p>The subject of the email can also be customised if you would like tracking added there as well.</p>
