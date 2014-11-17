<p>You have 2 options when it comes to sending the profile details - find the unique sender id of the profile stored in idibu and send that, or send the full user profile details in the post.</p>
<h1>
	Send the sender id as defined inside idibu</h1>
<table align="center" border="1" cellpadding="2" cellspacing="2" style="font-size: 13px; color: black; background-color: white; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 5px;">
	<tbody>
		<tr valign="top">
			<th scope="col">
				Required?</th>
			<th scope="col">
				Field Name</th>
			<th scope="col">
				Data Type</th>
			<th scope="col">
				Description</th>
		</tr>
		<tr valign="top">
			<td>
				Yes</td>
			<td>
				sender</td>
			<td>
				<a href="/docs/sender-profile-listing">See discovery service</a></td>
			<td>
				Identifies the sender profile to be used with this post<br />
				&nbsp;</td>
		</tr>
	</tbody>
</table>
<p>An example here is: &lt;sender id=&quot;31000290&quot; /&gt;</p>
<h1>
	Submit all sender info with the post</h1>
<p>In this instance all tags must be wrapped in the sender envelope.</p>
<table align="center" border="1" cellpadding="2" cellspacing="2" style="font-size: 13px; color: black; background-color: white; margin-top: 0px; margin-right: 0px; margin-bottom: 0px; margin-left: 5px;">
	<tbody>
		<tr valign="top">
			<th scope="col">
				Required?</th>
			<th scope="col">
				Field Name</th>
			<th scope="col">
				Data Type</th>
			<th scope="col">
				Description</th>
		</tr>
		<tr valign="top">
			<td>
				No</td>
			<td>
				expiryemails</td>
			<td>
				Values: Yes/No</td>
			<td>
				The system sends out emails alerting users when their job ads expire</td>
		</tr>
		<tr valign="top">
			<td>
				No</td>
			<td>
				team</td>
			<td>
				A valid team id (see discovery services)</td>
			<td>
				See explanation below of the team id tag</td>
		</tr>
		<tr valign="top">
			<td>
				No</td>
			<td>
				title</td>
			<td>
				Values: Mr/Mrs/Ms</td>
			<td>
				&nbsp;</td>
		</tr>
		<tr valign="top">
			<td>
				Yes</td>
			<td>
				name</td>
			<td>
				text</td>
			<td>
				First name of sender</td>
		</tr>
		<tr valign="top">
			<td>
				Yes</td>
			<td>
				lastname</td>
			<td>
				text</td>
			<td>
				Last name of sender</td>
		</tr>
		<tr valign="top">
			<td>
				Yes</td>
			<td>
				email</td>
			<td>
				text</td>
			<td>
				&nbsp;</td>
		</tr>
		<tr valign="top">
			<td>
				Yes</td>
			<td>
				company</td>
			<td>
				text</td>
			<td>
				Company name</td>
		</tr>
		<tr valign="top">
			<td>
				Yes</td>
			<td>
				phone</td>
			<td>
				text</td>
			<td>
				&nbsp;</td>
		</tr>
		<tr valign="top">
			<td>
				No</td>
			<td>
				fax</td>
			<td>
				text</td>
			<td>
				&nbsp;</td>
		</tr>
		<tr valign="top">
			<td>
				Yes</td>
			<td>
				www</td>
			<td>
				text</td>
			<td>
				&nbsp;</td>
		</tr>
		<tr valign="top">
			<td>
				No</td>
			<td>
				address1</td>
			<td>
				text</td>
			<td>
				&nbsp;</td>
		</tr>
		<tr valign="top">
			<td>
				No</td>
			<td>
				address2</td>
			<td>
				text</td>
			<td>
				&nbsp;</td>
		</tr>
		<tr valign="top">
			<td>
				No</td>
			<td>
				address3</td>
			<td>
				text</td>
			<td>
				&nbsp;</td>
		</tr>
		<tr valign="top">
			<td>
				Yes</td>
			<td>
				country</td>
			<td>
				text</td>
			<td>
				&nbsp;</td>
		</tr>
		<tr valign="top">
			<td>
				Yes</td>
			<td>
				postcode</td>
			<td>
				text</td>
			<td>
				&nbsp;</td>
		</tr>
	</tbody>
</table>
<p>&nbsp;</p>
<p>An example of this is:</p>
<pre>
<code>
<sender>
	<!-- below is the list of mandatory fields -->
	<name>John</name>
	<lastname>Doe</lastname>
	<email>john@doe.com</email>
	<company>One World Market</company>
	<phone>044424345324</phone>
	<www>http://some.website.com</www>
	<country>UK</country>
	<postcode>XXX111</postcode>
	<!-- below is the list of non-mandatory fields. -->
	<expiryemails>No</expiryemails><title></title>
	<address1>Some address</address1>
	<address2>Some address2</address2>
	<address3>Some address3</address3>
	<fax>044424345325</fax>
</sender>
</code></pre>
<p>Unless the posting system is tightly integrated into idibu (i.e., all sender ids have been fetched from idibu using the discovery service, and those ids are used when posting) it&#39;s advisable to always send the complete sender information, rather than the sender id. Our system will always try to match the name, last name and email to data already in our system before creating a new profile.</p>
<h2>
	Team Tag</h2>
<p>You can also send the team id to the sender part of the payload.</p>
<p>In that case, you&#39;ll need to add a TEAM tag with an id parameter specifying the team to which to assign the sender:</p>
<pre>
<code><sender>
	<!-- below is the list of mandatory fields -->
	<name>John</name>
	<lastname>Doe</lastname>
	<team id="10000">
	<email>john@doe.com</email>
	<!-- rest of the sender profile tags -->
	...
</team></sender>
</code></pre>
<p>The list of teams, offices and its IDs are available in the&nbsp;<a href="/docs/sender-profile-listing">discovery service</a>.</p>
<p>A couple of points when sending sender details.</p>
<ul>
	<li>
		If the sender already exists in the system, it is possible to send only the name, lastname and email address instead of the sender profile id to identify the sender in the system, albeit this practice isn&#39;t advisable as the request will fail if the sender isn&#39;t found and not all the required tags are in the payload.</li>
	<li>
		If you send the team tag the system analyses which profile this sender belongs to. If its different to the current placement, the system updates it.</li>
	<li>
		Sending a team tag with an id value of 0 (zero) will remove any profile from the team it is in, without affecting the quota assigned directly to that profile.</li>
	<li>
		All quota assignments are honored after a profiles is created, loaded or if it&#39;s team is changed.</li>
</ul>
<p>&nbsp;</p>
