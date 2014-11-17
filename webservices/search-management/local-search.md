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
<?xml version="1.0"?>
<idibu>
  <query>manager</query>
  <location>UK</location>
  <region></region>
  <postcode></postcode>
  <query_mode>OR</query_mode>
  <salarymin></salarymin>
  <salarymax></salarymax>
  <salaryper></salaryper>
  <jobtype></jobtype>
  <last_updated></last_updated>
  <max_results>25</max_results>
  <sector></sector>
</idibu>
</code>
</pre>
<h2>
	Response</h2>
<pre>
<code type="xml">
<?xml version="1.0" encoding="utf8"?>
<idibu generator="idibu" version="1.0">
  <response>
    <cv-entries>
      <cv-entry>
        <entry.info>
          <type>j</type>
          <src>LOCAL</src>
          <score>1</score>
          <fn>Firstname</fn>
          <ln>Lastname</ln>
          <id>LOCAL_12345678</id>
          <dist></dist>
          <avail></avail>
          <update>2012-01-27</update>
          <last_pos>HEAD OF MARKETING</last_pos>
          <loc>Guildford, UK</loc>
          <name>Firstname Lastname</name>
          <salary></salary>
        </entry.info>
        <doc>
          <snippets>
            <snippet>Skills: Branding, Direct marketing, Procurement, Marketing, Customer Relationship Management, Adobe Photoshop, Office support, Managed deliveries, Managed all campaigns, Managed a wide range of banners and microsites</snippet>
            <snippet>Current position: HEAD OF MARKETING</snippet>
            <snippet>Past: DEMAND CREATION SUPPORT at eCOMMERCE</snippet>
          </snippets>
        </doc>
        <aptrack-id>12345678</aptrack-id>
      </cv-entry>
    </cv-entries>
  </response>
  <status>success</status>
</idibu>
</code>
</pre>
