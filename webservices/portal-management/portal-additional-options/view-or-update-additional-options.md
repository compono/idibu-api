<p>The method allows to view or set additional options for each portal subscription:</p>
<ul>
  <li><strong><code>PostDuration</code></strong> - a default, fixed posting duration for the board - this means you can, for example, allow users to post jobs for 1 week only.<br/>To obtain a list of particular portal's available durations, use the <a href="https://github.com/oneworldmarket/idibu-api/blob/master/api-v3/board-specific-fields.md" target="_blank">board-specific-fields</a> webservice.<br/>This is not something that will work out-of-the-box inside the API - but it will on <a href="https://github.com/oneworldmarket/idibu-api/blob/master/api-v3/pcp.md" target="_blank">PCP</a>.</li>
  <li><strong><code>CostPerPost</code></strong> - a price per post that you can use to calculate an estimation of your users' advert budget spend when they post. Idibu can also use this data in monthly reports.</li>
  <li><strong><code>AutoUnsubscribeDate</code></strong> - the date when the account will be automatically unsubscribed from the job board.<br/>Format is <code>DD-MM-YYYY</code>.</li>
  <li><strong><code>DefaultTeams</code></strong> - a comma-separated list of IDs identifying teams for which the portal will be chosen as a default (or required - see <code>Forced</code> below) posting destination.<br/>To obtain team IDs, use the <a href="https://github.com/oneworldmarket/idibu-api/blob/master/webservices/user-management/list-teams.md" target="_blank">list-teams</a> webservice.</li>
  <li><strong><code>Forced</code></strong> - a boolean value deciding if the selected <code>DefaultTeams</code> should be forced to post to the portal (<code>true</code>) or not (<code>false</code>).</li>
  <li><strong><code>SectorFilter</code></strong> - a comma-separated list of IDs identifying job categories that are allowed to post to the board.<br/>To obtain a list of categories, refer to <a href="https://github.com/oneworldmarket/idibu-api/blob/master/api-v3/Sector-and-locations.md" target="_blank">this article</a>.</li>
</ul>
<h1>Parameters</h1>
<p>No additional parameters.</p>
<h1>Example - obtaining current setup</h1>
<p>To view the current settings, just fire a GET request to the webservice.</p>
<h2>Request</h2>
<pre><code>GET https://ws.idibu.com/ws/rest/v1/portals/517/additional-options?hash=YOUR_HASH</code></pre>
<h2>Response</h2>
<pre><code type="xml">&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
	&lt;response&gt;
		&lt;options&gt;
			&lt;option&gt;
				&lt;name&gt;PostDuration&lt;/name&gt;
				&lt;value&gt;1||7&lt;/value&gt;
			&lt;/option&gt;
			&lt;option&gt;
				&lt;name&gt;CostPerPost&lt;/name&gt;
				&lt;value&gt;12.5&lt;/value&gt;
			&lt;/option&gt;
			&lt;option&gt;
				&lt;name&gt;AutoUnsubscribeDate&lt;/name&gt;
				&lt;value&gt;2018-05-26&lt;/value&gt;
			&lt;/option&gt;
			&lt;option&gt;
				&lt;name&gt;DefaultTeams&lt;/name&gt;
				&lt;value&gt;2000748,2001250&lt;/value&gt;
			&lt;/option&gt;
			&lt;option&gt;
				&lt;name&gt;Forced&lt;/name&gt;
				&lt;value&gt;false&lt;/value&gt;
			&lt;/option&gt;
			&lt;option&gt;
				&lt;name&gt;SectorFilter&lt;/name&gt;
				&lt;value&gt;1,3,4&lt;/value&gt;
			&lt;/option&gt;
		&lt;/options&gt;
	&lt;/response&gt;
	&lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
<h1>Example - editing the options</h1>
<p>To edit or set the options, fire a POST request with an appropriate XML (see below) inside the <code>data</code> parameter.</p>
<h2>Request</h2>
<pre><code>POST https://ws.idibu.com/ws/rest/v1/portals/517/additional-options?hash=YOUR_HASH</code></pre>
<pre><code type="xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
	&lt;options&gt;
		&lt;option&gt;
			&lt;name&gt;PostDuration&lt;/name&gt;
			&lt;value&gt;1&lt;/value&gt;
		&lt;/option&gt;
		&lt;option&gt;
			&lt;name&gt;CostPerPost&lt;/name&gt;
			&lt;value&gt;9&lt;/value&gt;
		&lt;/option&gt;
		&lt;option&gt;
			&lt;name&gt;AutoUnsubscribeDate&lt;/name&gt;
			&lt;value&gt;25-12-2017&lt;/value&gt;
		&lt;/option&gt;
		&lt;option&gt;
			&lt;name&gt;DefaultTeams&lt;/name&gt;
			&lt;value&gt;2000748,2000749&lt;/value&gt;
		&lt;/option&gt;
		&lt;option&gt;
			&lt;name&gt;Forced&lt;/name&gt;
			&lt;value&gt;true&lt;/value&gt;
		&lt;/option&gt;
		&lt;option&gt;
			&lt;name&gt;SectorFilter&lt;/name&gt;
			&lt;value&gt;1,4,2806&lt;/value&gt;
		&lt;/option&gt;
	&lt;/options&gt;
&lt;/idibu&gt;
</code></pre>
<h2>Response</h2>
<pre><code type="xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
	&lt;response&gt;
		&lt;message&gt;Updated portal additional options&lt;/message&gt;
	&lt;/response&gt;
	&lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
