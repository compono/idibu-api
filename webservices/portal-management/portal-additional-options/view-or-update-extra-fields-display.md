The method allows to view or set the display of non-required (only!) extra fields on the portal:

- **`default`** - by default, all non-required extra fields are set up this way. Such fields will be optional when posting.
- **`required`** - makes the field mandatory when posting.
- **`hide`** - hides the field and ignores it when posting.

## Parameters
No additional parameters.

## Example - obtaining current setup
To view the current settings, just fire a GET request to the webservice.

### Request
`GET https://ws.idibu.com/ws/rest/v1/portals/517/extra-fields-display?hash=YOUR_HASH`

### Response
```xml
<idibu generator="idibu" version="1.0">
	<response>
		<fields>
			<field>
				<name>uaptemplate_517</name>
				<display>default</display>
			</field>
			<field>
				<name>idibu_salary</name>
				<display>required</display>
			</field>
		</fields>
	</response>
	<status>success</status>
</idibu>
```

## Example - editing the fields
To edit or set the options, fire a POST request with an appropriate XML (see below) inside the <code>data</code> parameter.

### Request
`POST https://ws.idibu.com/ws/rest/v1/portals/517/extra-fields-display?hash=YOUR_HASH`

```xml
<?xml version="1.0" encoding="utf8"?>
<idibu>
	<fields>
		<field>
			<name>uaptemplate_517</name>
			<display>hide</display>
		</field>
		<field>
			<name>idibu_salary</name>
			<display>required</display>
		</field>
	</fields>
</idibu>
```

### Response
```xml
<?xml version="1.0" encoding="UTF-8"?>
<idibu generator="idibu" version="1.0">
	<response>
		<message>Updated display settings</message>
	</response>
	<status>success</status>
</idibu>
```
