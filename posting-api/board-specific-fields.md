## Portal-specific data retrieval

This webservice facilitates the acquisition of data related to Portal objects, encompassing job boards, websites, and social media platforms suitable for job advertisement placement. Depending on how you've chosen to integrate your system with idibu (e.g. full API, and not utilising [Post Completion Pages](https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/pcp.md)), accessing and presenting specific data for individual Portals may be necessary.

### Listing Portals
This method enables the listing of Portals based on appropriate filtering and ordering criteria for a given account.

### Endpoint
#### `https://ws.idibu.com/clients/json.php`

### Query parameters
Parameter Name | Type restrictions | Required? | Notes
-- | -- | -- | --
`hash` | **String** | **Yes** | Hash of the idibu account to which the request pertains.
`action` | **String** | **Yes** | Must be set to `UserPortal`.
`class` | **String** | **Yes** | Must be set to `Portal`.
`format` | **String** | **Yes** | Must be set to `XML`.
`list` | **String (enum)**<br/><br/>Accepted values:<br/><code>all</code> - All available Portals<br/><code>subscribed</code> - Portals to which the account is subscribed<br/><code>unsubscribed</code> - Portals to which the account is not subscribed | **Yes** | Which Portals to list.

### Response format
```xml
<idibu>
  <boards>
    <board id="[integer]" last_modified="[string:date]" published="["true"|"false"]" subscribed="["true"|"false"]" allows_html="["true"|"false"]">
    <!-- "id" - portal id -->
    <!-- "last_modified" - last modification date (YYYY-MM-DD HH:mm:ss) -->
    <!-- "published" - whether the portal is published ("false" means it is not possible to post - might be completely disabled or temporarily under maintenance) -->
    <!-- "subscribed" - whether the account is currently subscribed ot the portal; displays only on "true" -->
    <!-- "allows_html" - whether HTML is allowed ("false" means idibu will automatically convert Job Description to plain text) -->
      <name>[string]</name> <!-- name of the portal -->
      <description>[string]</description> <!-- descripton of the portal -->
      <tags> <!-- industries related to the Portal; can be multiple -->
        <tag>[string]</tag>
      </tags>
    </board>
  </boards>
</idibu>
```

---

### Portal's detailed information
This method allows the retrieval of comprehensive details about a specific Portal, encompassing the essential data and extra fields required for successful postings.

### Endpoint
#### `https://ws.idibu.com/clients/json.php`

### Query parameters
Please maintain the order in which the parameters are listed!
Parameter Name | Type restrictions | Required? | Notes
-- | -- | -- | --
`hash` | **String** | **Yes** | Hash of the idibu account to which the request pertains.
`class` | **String** | **Yes** | Must be set to `Portal`.
`action` | **String** | **Yes** | Must be set to `showData`.
`boardID` | **Integer** | **Yes** | ID of the Portal to show.
`format` | **String** | **Yes** | Must be set to `XML`.
`country` | **2-letter ISO code** | No | Country code for Extra Field lookup.<br/>While this parameter is not required and will not affect most Portals, **it is strongly recommended to always include** as some Portals use country input in order to populate or filter their location Extra Fields with matching options.
`location` | **String** | No | Location for Extra Field lookup.<br/>While this parameter is not required and will not affect most Portals, **it is strongly recommended to always include** as some Portals require a Location string to be specified in order to populate their location Extra Fields with matching options. If no Location is provided (or the name matches no available options), the fields may not populate and therefore prevent the posting. Please use the full text name (not ID) of the sublocation.
`profileID` |  **Integer** | No | ID of the posting user.<br/>While this parameter is not required, **it is strongly recommended to always include as some Extra Field values may depend on each particular user's setup**. Refer to the [User Management Webservice](https://github.com/oneworldmarket/idibu-api/tree/master/webservices/user-management).
`title` | **String** | No | Title of the job.<br/>While this parameter is not required, **it is strongly recommended to always include** as some Portals use the job's title to filter or recommend some Extra Field values.

### Response format
```xml
<idibu>
  <boards>
    <board id="[integer]" last_modified="[string:date]" published="["true"|"false"]" allows_html="["true"|"false"]" supports_delete="["Yes"|"No"]">
    <!-- "id" - portal id -->
    <!-- "last_modified" - last modification date (YYYY-MM-DD HH:mm:ss) -->
    <!-- "published" - whether the portal is published ("false" means it is not possible to post - might be completely disabled or temporarily under maintenance) -->
    <!-- "allows_html" - whether HTML is allowed ("false" means idibu will automatically convert Job Description to plain text) -->
    <!-- "supports_delete" - whether the portal allows deleting of already posted jobs -->
      <name>[string]</name> <!-- name of the portal -->
      <description>[string]</description> <!-- descripton of the portal -->
      <tags> <!-- industries related to the Portal; can be multiple -->
        <tag>[string]</tag>
      </tags>
      <bid>[string]</bid> <!-- default tracking code for the portal; refer to https://github.com/oneworldmarket/idibu-api/blob/master/webservices/settings-management/application_url_tracking.md -->
      <liveauth>["yes"|"no"]</liveauth> <!-- if set to "yes", the portal supports the LiveAuth feature; refer to https://github.com/oneworldmarket/idibu-api/blob/master/webservices/portal-management/portal-subscription-management/LiveAuth-API.md -->
      <validators> <!-- value limits for the extra fields; refer to https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/board-specific-fields.md#extra-field-validators -->
        <rule type="[string:enum]" control="[integer]"> <!-- type of the validator (see below) ; and a number that defines the limit -->
          <field>[string]</field> <!-- name of the extra field -->
          <message>[string]</message> <!-- error message to display if the limit is violated -->
        </rule>
      </validators>
      <durations> <!-- available posting durations (in number of days) after which the posting will automatically expire; can be multiple; no options indicate infinite duration -->
        <duration value="[integer]">[string]</duration> <!-- number of days ; and the name of the option to display -->
      </durations>
      <extrafields> <!-- all extra fields assigned to the portal; refer to https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/board-specific-fields.md#extra-field-types -->
        <extrafield name="[string]" dynfield="[string]" description="[string]" type="[string:enum]" order="[integer]" multi="["true"|"false"]" validated="["true"|"false"]" required="["true"|"false"]">
        <!-- "name" - name of the extra field -->
        <!-- "dynfield" - name of the dynamic core field to which the field is connected; refer to https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/dyn-vars.md -->
        <!-- "description" - friendly name to display -->
        <!-- "type" - type of the field (see below) -->
        <!-- "order" - number that controls the order in which the fields should be displayed -->
        <!-- "multi" - whether the field allows multiple options to be selected; displays only on "true" -->
        <!-- "validated" - whether the field uses a validator (see above); displays only on "true" -->
        <!-- "required" - whether the field is required or optional; displays only on "true" -->	
        <!-- refer to https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/spec-data.md for more info on how each extra field data should be sent in the payload -->
          <data> <!-- only for "type=select" fields -->
            <option>Please select...</option> <!-- if an option has no id, it should only be displayed but not selectable -->
            <option id="[string]">[string]</option> <!-- the first string ("id") is the value to be sent in the field; the second one is the friendly name to be displayed -->
            <option id="[string]" parent="[string]">[string]</option> <!-- if the field is double-select, both "id" and "parent" values need sending -->
          </data>
        </extrafield>
      </extrafields>
      <dynfields> <!-- all dynamic core fields that the portal utilizes; refer to https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/dyn-vars.md --> 
        <dynfield name="[string:enum]" type="[string:enum]" description="[string]"/> <!-- name of the dynamic core field ; type of the connected extra field ; friendly name of the connected extra field -->
      </dynfields>
    </board>
  </boards>
</idibu>
```

## Extra Field Validators
Validators impose constraints on specific Extra Fields, ensuring successful postings. These include limits related to field length, content, numeric values, and data type.

### Field length
- `fieldMaxLength` - Maximum character count
- `fieldMinLength` - Minimum character count
- `fieldMaxWords` - Maximum word count
- `fieldMinWords` - Minimum word count
- `listHasMaxChoices` - Maximum choice count (only for `"type=select" multi="true"` fields)
- `listHasMinChoices` - Minimum choice count (only for `"type=select" multi="true"` fields)

### Field content
- `fieldWithoutLinks` - Restricts links in the field
- `fieldWithoutEmails` - Restricts email addresses in the field

### Numeric fields
- `intMaxSize` - Maximum allowed number
- `intMinSize` - Minimum allowed number

### Field data type
- `onlyNumbers` - Allows only numbers
- `fieldHasProperLink` - Allows valid URLs
- `validUKPostCode` - Allows valid UK post codes

## Extra Field Types
- `text` - Standard text field (no newlines)
- `textarea` - Standard text area (newlines allowed)
- `select` - Dropdown field (single- or double-select with one or multiple options)
- `hidden` - Non-visible field without user control

For more details on sending extra field data in the payload, refer to [spec-data documentation](https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/spec-data.md).
