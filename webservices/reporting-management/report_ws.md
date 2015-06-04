

<p>Method allows you to return an excel report, filtered by data you have specified.</p>
<h1>
	Filtering options</h1>
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
				<p class="p2">from</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">Yes</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">YYYY-MM-DD date of begining of the gathered data, i.e. 2015-05-01</p>
			</td>
		</tr>
		<tr>
			<td class="td1" valign="middle">
				<p class="p2">to</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">Yes</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">YYYY-MM-DD date of begining of the gathered data, i.e. 2015-05-31.</p>
			</td>
		</tr>
				<tr>
			<td class="td1" valign="middle">
				<p class="p2">offices</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">Numeric IDs of the offices to be included in the report. If no offices, teams or profiles specified, report will be generated for all users with sorted under their respective offices and teams</p>
			</td>
		</tr>
						<tr>
			<td class="td1" valign="middle">
				<p class="p2">teams</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">Numeric IDs of the teams to be included in the report. If no offices, teams or profiles specified, report will be generated for all users with sorted under their respective offices and teams</p>
			</td>
		</tr>
						<tr>
			<td class="td1" valign="middle">
				<p class="p2">profiles</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">Numeric IDs of the users to be included in the report. If no offices, teams or profiles specified, report will be generated for all users with sorted under their respective offices and teams</p>
			</td>
		</tr>
						<tr>
			<td class="td1" valign="middle">
				<p class="p2">include-inactive</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">Yes or No with No as default. If set to yes, will include data from users that did not make any posting in the specified reporting period.</p>
			</td>
		</tr>
		<tr>
			<td class="td1" valign="middle">
				<p class="p2">boards</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">Numeric IDs of the portals to be included in the report. If no portal ids specified, report will be generated for all portals subscribed on the specified account</p>
			</td>
		</tr>
		<tr>
			<td class="td1" valign="middle">
				<p class="p2">email</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">Yes</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">Email where the requested report should be emailed to.</p>
			</td>
		</tr>
				<tr>
			<td class="td1" valign="middle">
				<p class="p2">watchdog</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">When generating a report, you may wish to set it, so the very same report will be sent to the same person periodically. You need to name your watchdog, choose how often will it be sent and the period it will include (the original from to dates will be ignored once the watchdog report will be ready). The original report (that is triggering the watchdog) will respect the provided period.</p>
			</td>
		</tr>
	</tbody>
</table>
<!--break-->
<h1>
	Example</h1>
<h2>
	Request</h2>
<pre>
<code>
<code type="xml">
POST http://ws.idibu.com/ws/rest/v1/reports/(REPORT NAME)?hash=

BASIC:

&lt;idibu&gt;
    &lt;date-range&gt;
        &lt;from&gt;2015-05-01&lt;/from&gt;
        &lt;to&gt;2015-05-28&lt;/to&gt;
    &lt;/date-range&gt;
    &lt;profiles&gt;
        &lt;offices /&gt;
        &lt;teams /&gt;
        &lt;profiles /&gt;
    &lt;/profiles&gt;
    &lt;boards /&gt;
    &lt;email&gt;yourclient@hisserver.com&lt;/email&gt;
&lt;/idibu&gt;

WITH MORE PARAMETERS:

&lt;idibu&gt;
    &lt;date-range&gt;
        &lt;from&gt;2015-05-01&lt;/from&gt;
        &lt;to&gt;2015-05-28&lt;/to&gt;
    &lt;/date-range&gt;
    &lt;profiles&gt;
        &lt;offices&gt;
			&lt;office&gt;1000&lt;/office&gt;	
		&lt;/offices&gt;
        &lt;teams&gt;
			&lt;team&gt;1001&lt;/team&gt;
			&lt;team&gt;1002&lt;/team&gt;
			&lt;team&gt;1003&lt;/team&gt;	
		&lt;/teams&gt;
        &lt;profiles&gt;
			&lt;profile&gt;1004&lt;/profile&gt;
			&lt;profile&gt;1005&lt;/profile&gt;
			&lt;profile&gt;1006&lt;/profile&gt;
		&lt;/profiles&gt;
        &lt;include-inactive&gt;no&lt;/include-inactive&gt;
    &lt;/profiles&gt;
    &lt;boards&gt;
        &lt;board&gt;1599&lt;/board&gt;
    &lt;/boards&gt;
    &lt;email&gt;yourclient@hisserver.com&lt;/email&gt;
    &lt;watchdog&gt;
         &lt;name&gt;new_watchdog&lt;/name&gt;
         &lt;frequency&gt;monthly&lt;/frequency&gt;
         &lt;range&gt;month&lt;/range&gt;
    &lt;/watchdog&gt;
&lt;/idibu&gt;
</code></pre>
