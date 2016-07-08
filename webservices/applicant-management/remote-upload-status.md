Upon processing a candidate the external system should send an HTTP POST request to the following endpoint:<br><br>
<code>
http://ws.idibu.com/ws/rest/v1/applicant-status/:applicant-id?hash=:hash
</code><br><br>
The request should contain an XML payload encapsulated in a x-www-form-urlencoded request, in a field called data, like so:
<br><br>
POST /ws/rest/v1/applicant-status/123?hash=456
<br><br>
Host: ws.idibu.com
Content-Type: application/x-www-form-urlencoded
<br>
data=%3Cxml%3Epayload%3C%2Fxml%3E…
<br><br>
The XML payload should follow the specified format:
<br>
<pre>
<code type="xml">
&lt;applicant&gt;
	&lt;status&gt;:status&lt;/status&gt;
	&lt;remote-id&gt;:remote-id&lt;/remote-id&gt;
	&lt;error-message&gt;:error-message&lt;/error-message&gt;
	&lt;date-processed&gt;:date-processed&lt;/date-processed&gt;
&lt;/applicant&gt;
&lt;/code&gt;
</code>
</pre>
<br>
If the status is successfully stored, the endpoint will return a success status message (may also contain other information):
<br>
<pre>
<code type="xml">
&lt;idibu&gt;
&lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre><br>
The fields used in the request are:<br>

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
				<p class="p2">hash</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">Yes</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">Client API hash</p>
			</td>
		</tr>
		<tr>
			<td class="td1" valign="middle">
				<p class="p2">applicant-id</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">Yes</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">Applicant ID (X-iTrackID header in the AppTrack forwarded email)</p>
			</td>
		</tr>
		<tr>
			<td class="td1" valign="middle">
				<p class="p2">status</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">Yes</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">String describing the status of candidate processing, expected either success or fail</p>
			</td>
		</tr>
		<tr>
			<td class="td1" valign="middle">
				<p class="p2">remote-id</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">Any string to identify the applicant in remote system</p>
			</td>
		</tr>
		<tr>
			<td class="td1" valign="middle">
				<p class="p2">error-message</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">Error message detailing the problem that occurred while processing the application, expected on fail status</p>
			</td>
		</tr>
		<tr>
			<td class="td1" valign="middle">
				<p class="p2">date-processed</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">Date and time at which the application was processed, if empty current date is used, expected in YYYY-MM-DD hh:mm:ss format</p>
			</td>
		</tr>
	</tbody>
</table>
<br>
Example of a correct request for a successfully processed application:
<br>
<code type="xml">
&lt;applicant&gt;
	&lt;status&gt;success&lt;/status&gt;
	&lt;date-processed&gt;2016-06-03 12:11:59&lt;/date-processed&gt;
&lt;/applicant&gt;
</code>
</br>
Example of a correct request for an unsuccessfully processed application:
<br>
<code type="xml">
&lt;applicant&gt;
	&lt;status&gt;fail&lt;/status&gt;
	&lt;error-message&gt;Candidate application has been eaten by a stray dog&lt;/error-message&gt;
	&lt;date-processed&gt;2016-06-03 13:07:34&lt;/date-processed&gt;
&lt;/applicant&gt;
</code>
</br>
Sending multiple requests for the same applicant will result in updating the information in idibu.
It is also possible to then remotely check the status of the candidate based on idibu’s candiate ID or based on the remote ID provided:

Option 1

GET /ws/rest/v1/applicant-status/:id?hash=:hash

Returns data for a particular AppTrack id :id.

Option 2
GET /ws/rest/v1/applicant-status?hash=:hash


Returns all client applicants' statuses (as in all WSes limited to 10 by default, can be browsed with offset and limit params).
Option 3
GET /ws/rest/v1/applicant-status?hash=:hash&remote-id=:remote-id


Returns applicants' statuses matching the :remote-id provided. Wildcard * can be used.
