<p>Method returns applicant lists. There are two versions:<br />
	<br />
	<b>GET</b> - http://ws.idibu.com/ws/rest/v1/applicants/? - for quick manual testing<br />
	<b>POST</b> - http://ws.idibu.com/ws/rest/v1/applicants/list/? - to be used in your production environmet</p>
<h1>
	Parameters</h1>
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
				<p class="p2">offset</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">numeric offset from where to fetch applicants, default is 0</p>
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
				<p class="p2">number of applicants to return in response, default is 10</p>
			</td>
		</tr>
		<tr>
			<td class="td1" valign="middle">
				<p class="p2">board-id</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">filter applicants by board, multiple allowed, comma separated&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td class="td1" valign="middle">
				<p class="p2">user-id</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">filter applicants by user, who posted adverts, multiple allowed, comma separated&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td class="td1" valign="middle">
				<p class="p2">job-id</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">filter applicants by job, multiple allowed, comma separated&nbsp;</p>
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
				<p class="p2">filter applicants by job reference</p>
			</td>
		</tr>
		<tr>
			<td class="td1" valign="middle">
				<p class="p2">status</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">filter applicants by status name (note that you can get list of available statuses from settings service)</p>
			</td>
		</tr>
		<tr>
			<td class="td1" valign="middle">
				<p class="p2">advert_live</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">filter applicants by Adverts live since at least X days. For example if you select 7, then you will get a list of all applicants for jobs currently live and jobs that expired no longer then 7 days ago. Additional filters will also be considered.</p>
			</td>
		</tr>
		<tr>
			<td class="td1" valign="middle">
				<p class="p2">after_date</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">to filter webservice to show applicants that appied after specified date. Please use YYYY-MM-DD format.</p>
			</td>
		</tr>
		<tr>
			<td class="td1" valign="middle">
				<p class="p2">before_date</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">to filter webservice to show applicants that appied before specified date. Please use YYYY-MM-DD format.</p>
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
GET:
http://ws.idibu.com/ws/rest/v1/applicants?hash=<your hash>&count=10&status=Unread
</code>
<code>
POST:
http://ws.idibu.com/ws/rest/v1/applicants/list?hash=<your hash>&count=10&status=Unread
</code>
</pre>
<h2>
	Response</h2>
<pre>


<code type="xml">
&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
  &lt;response&gt;
    &lt;applicants&gt;
      &lt;applicant&gt;
        &lt;id&gt;33078101&lt;/id&gt;
        &lt;email&gt;contact1234567@gmail.com&lt;/email&gt;
        &lt;name&gt;Jobs On-Line&lt;/name&gt;
        &lt;job&gt;
          &lt;id&gt;33004367&lt;/id&gt;
          &lt;reference&gt;VTEST#1&lt;/reference&gt;
        &lt;/job&gt;
        &lt;portal-id&gt;517&lt;/portal-id&gt;
        &lt;date&gt;2010-04-28 16:31:01&lt;/date&gt;
        &lt;status&gt;Unread&lt;/status&gt;
      &lt;/applicant&gt;
      &lt;applicant&gt;
        &lt;id&gt;33078110&lt;/id&gt;
        &lt;email&gt;groupby@yandex.ru&lt;/email&gt;
        &lt;name&gt;&amp;auml;&amp;Ntilde;&amp;Ocirc;&amp;Igrave;&amp;Iuml;&amp;times; &amp;divide;&amp;Eacute;&amp;Ocirc;&amp;Aacute;&amp;Igrave;&amp;Eacute;&amp;Ecirc;&lt;/name&gt;
        &lt;job&gt;
          &lt;id&gt;33004367&lt;/id&gt;
          &lt;reference&gt;VTEST#1&lt;/reference&gt;
        &lt;/job&gt;
        &lt;portal-id&gt;517&lt;/portal-id&gt;
        &lt;date&gt;2010-04-28 16:41:01&lt;/date&gt;
        &lt;status&gt;Unread&lt;/status&gt;
      &lt;/applicant&gt;
      &lt;applicant&gt;
        &lt;id&gt;33117965&lt;/id&gt;
        &lt;email&gt;md.xytop@gmail.com&lt;/email&gt;
        &lt;name&gt;Vitaly Dyatlov&lt;/name&gt;
        &lt;job&gt;
          &lt;id&gt;33007149&lt;/id&gt;
          &lt;reference&gt;myreference&lt;/reference&gt;
        &lt;/job&gt;
        &lt;portal-id&gt;517&lt;/portal-id&gt;
        &lt;date&gt;2010-05-27 20:15:03&lt;/date&gt;
        &lt;status&gt;Unread&lt;/status&gt;
      &lt;/applicant&gt;
      &lt;applicant&gt;
        &lt;id&gt;33117978&lt;/id&gt;
        &lt;email&gt;md.xytop@gmail.com&lt;/email&gt;
        &lt;name&gt;Vitaly Dyatlov&lt;/name&gt;
        &lt;job&gt;
          &lt;id&gt;33007149&lt;/id&gt;
          &lt;reference&gt;myreference&lt;/reference&gt;
        &lt;/job&gt;
        &lt;portal-id&gt;517&lt;/portal-id&gt;
        &lt;date&gt;2010-05-27 20:21:03&lt;/date&gt;
        &lt;status&gt;Unread&lt;/status&gt;
      &lt;/applicant&gt;
      &lt;applicant&gt;
        &lt;id&gt;33126212&lt;/id&gt;
        &lt;email&gt;md.xytop@gmail.com&lt;/email&gt;
        &lt;name&gt;Vitaly Dyatlov&lt;/name&gt;
        &lt;job&gt;
          &lt;id&gt;33007149&lt;/id&gt;
          &lt;reference&gt;myreference&lt;/reference&gt;
        &lt;/job&gt;
        &lt;portal-id&gt;517&lt;/portal-id&gt;
        &lt;date&gt;2010-06-01 19:03:04&lt;/date&gt;
        &lt;status&gt;Unread&lt;/status&gt;
      &lt;/applicant&gt;
      &lt;applicant&gt;
        &lt;id&gt;33208394&lt;/id&gt;
        &lt;email&gt;vitaly@idibu.com&lt;/email&gt;
        &lt;name&gt;Vitaly Dyatlov&lt;/name&gt;
        &lt;job&gt;
          &lt;id&gt;33009925&lt;/id&gt;
          &lt;reference&gt;vitref&lt;/reference&gt;
        &lt;/job&gt;
        &lt;portal-id&gt;517&lt;/portal-id&gt;
        &lt;date&gt;2010-07-12 17:07:06&lt;/date&gt;
        &lt;status&gt;Unread&lt;/status&gt;
      &lt;/applicant&gt;
      &lt;applicant&gt;
        &lt;id&gt;33208464&lt;/id&gt;
        &lt;email&gt;vitaly@idibu.com&lt;/email&gt;
        &lt;name&gt;Vitaly Dyatlov&lt;/name&gt;
        &lt;job&gt;
          &lt;id&gt;33009929&lt;/id&gt;
          &lt;reference&gt;vitref2&lt;/reference&gt;
        &lt;/job&gt;
        &lt;portal-id&gt;517&lt;/portal-id&gt;
        &lt;date&gt;2010-07-12 17:35:06&lt;/date&gt;
        &lt;status&gt;Unread&lt;/status&gt;
      &lt;/applicant&gt;
      &lt;applicant&gt;
        &lt;id&gt;33208471&lt;/id&gt;
        &lt;email&gt;vitaly@idibu.com&lt;/email&gt;
        &lt;name&gt;Vitaly Dyatlov&lt;/name&gt;
        &lt;job&gt;
          &lt;id&gt;33009929&lt;/id&gt;
          &lt;reference&gt;vitref2&lt;/reference&gt;
        &lt;/job&gt;
        &lt;portal-id&gt;517&lt;/portal-id&gt;
        &lt;date&gt;2010-07-12 17:37:06&lt;/date&gt;
        &lt;status&gt;Unread&lt;/status&gt;
      &lt;/applicant&gt;
      &lt;applicant&gt;
        &lt;id&gt;33208603&lt;/id&gt;
        &lt;email&gt;vitaly@idibu.com&lt;/email&gt;
        &lt;name&gt;Vitaly Dyatlov&lt;/name&gt;
        &lt;job&gt;
          &lt;id&gt;33009929&lt;/id&gt;
          &lt;reference&gt;vitref2&lt;/reference&gt;
        &lt;/job&gt;
        &lt;portal-id&gt;517&lt;/portal-id&gt;
        &lt;date&gt;2010-07-12 18:39:04&lt;/date&gt;
        &lt;status&gt;Unread&lt;/status&gt;
      &lt;/applicant&gt;
      &lt;applicant&gt;
        &lt;id&gt;33208489&lt;/id&gt;
        &lt;email&gt;vitaly@idibu.com&lt;/email&gt;
        &lt;name&gt;Vitaly Dyatlov&lt;/name&gt;
        &lt;job&gt;
          &lt;id&gt;33009931&lt;/id&gt;
          &lt;reference&gt;vitref3&lt;/reference&gt;
        &lt;/job&gt;
        &lt;portal-id&gt;517&lt;/portal-id&gt;
        &lt;date&gt;2010-07-12 17:43:07&lt;/date&gt;
        &lt;status&gt;Unread&lt;/status&gt;
      &lt;/applicant&gt;
    &lt;/applicants&gt;
    &lt;total&gt;1645&lt;/total&gt;
  &lt;/response&gt;
  &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
