<p>You have 2 options when it comes to sending the profile details - find the unique sender id of the profile stored in idibu and send that, or send the full user profile details in the post. Refer to the <a href="/docs/v2/webservices/user-management">User Management Webservice</a> for more info.</p>

# Send the sender id as defined inside idibu

<table align="center" border="1" cellpadding="2" cellspacing="2" style={{ fontSize: '13px', color: 'black', backgroundColor: 'white', marginTop: '0px', marginRight: '0px', marginBottom: '0px', marginLeft: '5px' }}>
	<tbody>
		<tr valign="top">
			<th scope="col">Required?</th>
			<th scope="col">Field Name</th>
			<th scope="col">Data Type</th>
			<th scope="col">Description</th>
		</tr>
		<tr valign="top">
			<td>Yes</td>
			<td>sender</td>
			<td>To get a list of the sender profile in your account including the unique ids use: 
<code>https://ws.idibu.com/clients/api/enum.php?enum=Sender&source=mine&hash=[INSERT LOGIN HASH HERE]</code></td>
			<td>Identifies the sender profile to be used with this post</td>
		</tr>
	</tbody>
</table>

An example here is: `<sender id="31000290" />`

# Submit all sender info with the post

<p>In this instance all tags must be wrapped in the sender envelope.</p>

<table align="center" border="1" cellpadding="2" cellspacing="2" style={{ fontSize: '13px', color: 'black', backgroundColor: 'white', marginTop: '0px', marginRight: '0px', marginBottom: '0px', marginLeft: '5px' }}>
	<tbody>
		<tr valign="top">
			<th scope="col">Required?</th>
			<th scope="col">Field Name</th>
			<th scope="col">Data Type</th>
			<th scope="col">Description</th>
		</tr>
		<tr valign="top">
			<td>No</td>
			<td>expiryemails</td>
			<td>Values: Yes/No</td>
			<td>The system sends out emails alerting users when their job ads expire</td>
		</tr>
		<tr valign="top">
			<td>No</td>
			<td>team</td>
			<td>A valid team id (see discovery services)</td>
			<td>See explanation below of the team id tag</td>
		</tr>
		<tr valign="top">
			<td>No</td>
			<td>title</td>
			<td>Values: Mr/Mrs/Ms</td>
			<td>&nbsp;</td>
		</tr>
		<tr valign="top">
			<td>Yes</td>
			<td>name</td>
			<td>text</td>
			<td>First name of sender</td>
		</tr>
		<tr valign="top">
			<td>Yes</td>
			<td>lastname</td>
			<td>text</td>
			<td>Last name of sender</td>
		</tr>
		<tr valign="top">
			<td>Yes</td>
			<td>email</td>
			<td>text</td>
			<td>&nbsp;</td>
		</tr>
		<tr valign="top">
			<td>Yes</td>
			<td>company</td>
			<td>text</td>
			<td>Company name</td>
		</tr>
		<tr valign="top">
			<td>Yes</td>
			<td>phone</td>
			<td>text</td>
			<td>&nbsp;</td>
		</tr>
		<tr valign="top">
			<td>No</td>
			<td>fax</td>
			<td>text</td>
			<td>&nbsp;</td>
		</tr>
		<tr valign="top">
			<td>Yes</td>
			<td>www</td>
			<td>text</td>
			<td>&nbsp;</td>
		</tr>
		<tr valign="top">
			<td>No</td>
			<td>address1</td>
			<td>text</td>
			<td>&nbsp;</td>
		</tr>
		<tr valign="top">
			<td>No</td>
			<td>address2</td>
			<td>text</td>
			<td>&nbsp;</td>
		</tr>
		<tr valign="top">
			<td>No</td>
			<td>address3</td>
			<td>text</td>
			<td>&nbsp;</td>
		</tr>
		<tr valign="top">
			<td>Yes</td>
			<td>country</td>
			<td>text</td>
			<td>&nbsp;</td>
		</tr>
		<tr valign="top">
			<td>Yes</td>
			<td>postcode</td>
			<td>text</td>
			<td>&nbsp;</td>
		</tr>
	</tbody>
</table>

<p>An example of this is:</p>

```xml<sender>
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
```
<p>Unless the posting system is tightly integrated into idibu (i.e., all sender ids have been fetched from idibu using the discovery service, and those ids are used when posting) it's advisable to always send the complete sender information, rather than the sender id. Our system will always try to match the name, last name and email to data already in our system before creating a new profile.</p>

<h2>Team Tag</h2>

<p>You can also send the team id to the sender part of the payload.</p>

<p>In that case, you'll need to add a TEAM tag with an id parameter specifying the team to which to assign the sender:</p>

```xml<sender>
  <!-- below is the list of mandatory fields -->
  <name>John</name>
  <lastname>Doe</lastname>
  <team id="10000">
  <email>john@doe.com</email>
  <!-- rest of the sender profile tags -->
  ...
  </team>
</sender>
```
The list of teams, offices and its IDs are available in:
`https://ws.idibu.com/clients/api/enum.php?enum=Sender&source=mine&hash=[INSERT LOGIN HASH HERE]`

<p>A couple of points when sending sender details.</p>

- If the sender already exists in the system, it is possible to send only the name, lastname and email address instead of the sender profile id to identify the sender in the system, albeit this practice isn't advisable as the request will fail if the sender isn't found and not all the required tags are in the payload.
- If you send the team tag the system analyses which profile this sender belongs to. If its different to the current placement, the system updates it.
- Sending a team tag with an id value of 0 (zero) will remove any profile from the team it is in, without affecting the quota assigned directly to that profile.
- All quota assignments are honored after a profiles is created, loaded or if it's team is changed.

<a href="/docs/v2/posting-api/jobidvsjobref.md">Next article tells you about the difference between idibu id and client reference.</a>


