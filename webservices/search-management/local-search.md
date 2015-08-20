<p>Method searches through local database of client applicants</p>
<h1>
	Parameters</h1>
<p>No additional parameters for this request</p>
<h1>
	Possible values:</h1>
<table>
	<tbody>
		<tr>
			<th>
				Param</th>
			<th>
				Values</th>
		</tr>
		<tr>
			<td>
				query</td>
			<td>
				any sequence of words you want</td>
		</tr>
		<tr>
			<td>
				location</td>
			<td>
				Country code to search in</td>
		</tr>
		<tr>
			<td>
				region</td>
			<td>
				Region in country to search in - this a freetext search location</td>
		</tr>
		<tr>
			<td>
				postcode</td>
			<td>
				Postal code of location where you want to search for applicant</td>
		</tr>
		<tr>
			<td>
				radius</td>
			<td>
				Search radius in miles</td>
		</tr>
		<tr>
			<td>
				query_mode</td>
			<td>
				Grouping method of words in query. Can be one of these values: AND, OR</td>
		</tr>
		<tr>
			<td>
				salarymin</td>
			<td>
				Minimal salary which applicant wants, should be an integer</td>
		</tr>
		<tr>
			<td>
				salarymax</td>
			<td>
				Maximal salary which applicant wants, should be an integer</td>
		</tr>
		<tr>
			<td>
				salaryper</td>
			<td>
				Can be one of these values: annual, hourly. Please not that if applicant has an hourly salary and you are searching by annual salary or vice versa - applicant will not be included in result set</td>
		</tr>
		<tr>
			<td>
				jobtype</td>
			<td>
				Can be one of these values: perm, cont. perm - permanent. cont - contract</td>
		</tr>
		<tr>
			<td>
				last_updated</td>
			<td>
				Number of days left since a CV was sent/updated</td>
		</tr>
		<tr>
			<td>
				max_results</td>
			<td>
				Maximal number of results to return</td>
		</tr>
		<tr>
			<td>
				sector</td>
			<td>
				Possible values: accounting, automotive, aviation, construction, consultancy, customer_service, defence, distribution, education, electronics, engineering, graduate, health, hr, it, insurance, legal, transport, manufacturing, marketing, media, public_sector, recruitment, retail, sales, scientific, telecomms, training, travel</td>
		</tr>
	</tbody>
</table>
<h1>
	Example of searching</h1>
<h2>
	Request</h2>
<pre>
<code>
POST http://ws.idibu.com/ws/rest/v1/search/local?hash=<your hash>
</code>
<code type="xml">
&lt;?xml version=&quot;1.0&quot;?&gt;
&lt;idibu&gt;
  &lt;query&gt;manager&lt;/query&gt;
  &lt;location&gt;UK&lt;/location&gt;
  &lt;region&gt;&lt;/region&gt;
  &lt;postcode&gt;&lt;/postcode&gt;
  &lt;radius&gt;&lt;/postcode&gt;
  &lt;query_mode&gt;OR&lt;/query_mode&gt;
  &lt;salarymin&gt;&lt;/salarymin&gt;
  &lt;salarymax&gt;&lt;/salarymax&gt;
  &lt;salaryper&gt;&lt;/salaryper&gt;
  &lt;jobtype&gt;&lt;/jobtype&gt;
  &lt;last_updated&gt;&lt;/last_updated&gt;
  &lt;max_results&gt;25&lt;/max_results&gt;
  &lt;sector&gt;&lt;/sector&gt;
&lt;/idibu&gt;
</code>
</pre>
<h2>
	Response</h2>
<pre>
<code type="xml">
&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
  &lt;response&gt;
    &lt;cv-entries&gt;
      &lt;cv-entry&gt;
        &lt;entry.info&gt;
          &lt;type&gt;j&lt;/type&gt;
          &lt;src&gt;LOCAL&lt;/src&gt;
          &lt;score&gt;1&lt;/score&gt;
          &lt;fn&gt;Firstname&lt;/fn&gt;
          &lt;ln&gt;Lastname&lt;/ln&gt;
          &lt;id&gt;LOCAL_12345678&lt;/id&gt;
          &lt;dist&gt;&lt;/dist&gt;
          &lt;avail&gt;&lt;/avail&gt;
          &lt;update&gt;2012-01-27&lt;/update&gt;
          &lt;last_pos&gt;HEAD OF MARKETING&lt;/last_pos&gt;
          &lt;loc&gt;Guildford, UK&lt;/loc&gt;
          &lt;name&gt;Firstname Lastname&lt;/name&gt;
          &lt;salary&gt;&lt;/salary&gt;
        &lt;/entry.info&gt;
        &lt;doc&gt;
          &lt;snippets&gt;
            &lt;snippet&gt;Skills: Branding, Direct marketing, Procurement, Marketing, Customer Relationship Management, Adobe Photoshop, Office support, Managed deliveries, Managed all campaigns, Managed a wide range of banners and microsites&lt;/snippet&gt;
            &lt;snippet&gt;Current position: HEAD OF MARKETING&lt;/snippet&gt;
            &lt;snippet&gt;Past: DEMAND CREATION SUPPORT at eCOMMERCE&lt;/snippet&gt;
          &lt;/snippets&gt;
        &lt;/doc&gt;
        &lt;aptrack-id&gt;12345678&lt;/aptrack-id&gt;
      &lt;/cv-entry&gt;
    &lt;/cv-entries&gt;
  &lt;/response&gt;
  &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code>
</pre>

You can check the total number of candidates in the selected account:

<h1>
	Example of searching</h1>
<h2>
	Request</h2>
<pre>
<code>
POST http://ws.idibu.com/ws/rest/v1/search/local-cvs-count?hash=<your hash>
</code>
