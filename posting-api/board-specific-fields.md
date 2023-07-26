This webservice allows to obtain data relating to Portal objects - job boards, websites, social media where job adverts can be posted. Depending on how you're integrating your system with idibu (e.g. not utilizing [Post Completion Pages](https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/pcp.md)), you may need to obtain and present to your users all the data specific to particular Portals.

## Listing Portals
This method allows to list appropriately filtered and ordered Portals available for a given account.

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

## Portal's detailed info
This method allows to obtain more detailed information about a particular Portal. This is the main method of obtaining all the extra fields and data specific to the Portal, required to perform a successful posting.

### Endpoint
#### `https://ws.idibu.com/clients/json.php`

### Query parameters
Parameter Name | Type restrictions | Required? | Notes
-- | -- | -- | --
`hash` | **String** | **Yes** | Hash of the idibu account to which the request pertains.
`action` | **String** | **Yes** | Must be set to `showData`.
`boardID` | **Integer** | **Yes** | ID of the Portal to show.
`class` | **String** | **Yes** | Must be set to `Portal`.
`format` | **String** | **Yes** | Must be set to `XML`.
`country` | **2-letter ISO code** | No | Country to look up the Extra Fields with.<br>While this parameter is not required and will not affect most Portals, **it is strongly recommended to always include** as some Portals use country input in order to populate or filter their location Extra Fields with matching options.
`location` | **String** | No | Location to look up the Extra Fields with.<br>While this parameter is not required and will not affect most Portals, **it is strongly recommended to always include** as some Portals require a Location string to be specified in order to populate their location Extra Fields with matching options. If no Location is provided (or the name matches no available options), the fields may not populate and therefore prevent the posting.
`profileID` |  **Integer** | No | ID of the person posting the job.<br>While this parameter is not required, **it is strongly recommended to always include** as some Extra Field values may depend on each particular user's setup.<br/>Refer to the [User Management Webservice](https://github.com/oneworldmarket/idibu-api/tree/master/webservices/user-management).
`title` | **String** | No | Title of the job.<br>While this parameter is not required, **it is strongly recommended to always include** as some Portals use the job's title to filter or recommend some Extra Field values.

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
Validators are limits that should be applied to certain Extra Fields; otherwise, the posting will most likely fail.

### Field length
- `fieldMaxLength` - maximum character count
- `fieldMinLength` - minimum character count
- `fieldMaxWords` - maximum word count
- `fieldMinWords` - minimum word count
- `listHasMaxChoices` - maximum choice count (only for `"type=select" multi="true"` fields)
- `listHasMinChoices` - minimum choice count (only for `"type=select" multi="true"` fields)

### Field content
- `fieldWithoutLinks` - if set to `1`, the field cannot contain any links
- `fieldWithoutEmails` - if set to `1`, the field cannot contain any e-mail addresses

### Numeric fields
- `intMaxSize` - maximum allowed number
- `intMinSize` - minimum allowed number

### Field data type
- `onlyNumbers` - if set to `1`, only numbers are allowed in the field
- `fieldHasProperLink` - if set to `1`, only valid URLs are allowed in the field
- `validUKPostCode` - if set to `1`, only valid UK post codes are allowed in the field

## Extra Field Types
- `text` - a standard text field (newlines not allowed)
- `textarea` - a standard text area (newlines allowed)
- `select` - a dropdown field (can be single- or double-select with only one or multiple options allowed)
- `hidden` - the field should not be visible in the interface and the user should have no control over the value
