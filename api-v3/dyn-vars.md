<p><strong>The API uses what we call Dynamic Core Fields (DCF). </strong></p>
<p>These fields are not in the group of core fields, and are not needed in order to successfully post a job, but makes integrating and posting to boards a little easier. These fields are shared among the boards, you can find out which ones by using the <a href="https://github.com/oneworldmarket/idibu-api/blob/master/api-v3/spec-data.md">board discovery service</a>.</p>
<p>The purpose of these fields is to aggregate data repeated in the boards extra fields, while still allowing for customization on a per board basis when required.</p>
<p>Whenever a DCF is present in the XML payload, if they are used by the different boards to which the client intends to post, its values are used to fill the corresponding extra fields when those are not present in the request.</p>
<p>So for example, many boards will accept a text version of the start date - so if you&#39;d like &#39;ASAP&#39; to appear as the start date rather than an actual date, sending this through via the &quot;startDateOverride&quot; field means all boards supporting this have their extra fields auto-propagated. Below is the field list, and you can find examples of its usage in the <a href="https://github.com/oneworldmarket/idibu-api/tree/master/api-v3/examples">examples page</a>.</p>
<table align="center" border="1" cellpadding="2" cellspacing="2" style="font-size: 13px; color: black; background-color: white; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 5px; " width="90%">
	<tbody>
		<tr valign="top">
			<th scope="col">
				Field Name</th>
			<th scope="col">
				Data Type</th>
			<th scope="col">
				Description</th>
		</tr>
		<tr valign="top">
			<td>
				job_time</td>
			<td>
				numeric (Values: 1 for part time,<br />
				2 for full time)</td>
			<td>
				Job Time/Type. Idetifies the corresponding field whenever it&#39;s not possible to map the Board extra field to the corresponding idibu core field. You need to enter <job_time>2</job_time> among the <job> tags. In example after the <description> tag.</description></job></td>
		</tr>
		<tr valign="top">
			<td>
				startDateOverride</td>
			<td>
				text</td>
			<td>
				Start Date Description/Override</td>
		</tr>
		<tr valign="top">
			<td>
				salaryOverride</td>
			<td>
				text</td>
			<td>
				Salary&nbsp;Description/Override. Please provide this tag below the other Salary override tags.</td>
		</tr>
		<tr valign="top">
			<td>
				PostCode</td>
			<td>
				text</td>
			<td>
				Post Code</td>
		</tr>
		<tr valign="top">
			<td>
				app_url</td>
			<td>
				text</td>
			<td>
				Application URL<br />
				&nbsp;</td>
		</tr>
	</tbody>
</table>
<p>&nbsp;</p>
