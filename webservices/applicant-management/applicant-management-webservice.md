# Applicant Management Webservice
  * **[Listing Applicants](#listing-applicants)**
    + [Endpoint](#endpoint)
    + [Available methods](#available-methods)
    + [Query parameters](#query-parameters)
    + [Response format](#response-format)

  * **[Applicant's detailed view](#applicants-detailed-view)**
    + [Endpoint](#endpoint-1)
    + [Available methods](#available-methods-1)
    + [Query parameters](#query-parameters-1)
    + [Response format](#response-format-1)

  * **[Adding a new Applicant](#adding-a-new-applicant)**
    + [Endpoint](#endpoint-2)
    + [Available methods](#available-methods-2)
    + [Query parameters](#query-parameters-2)
    + [Query format](#query-format)
    + [Response format](#response-format-2)

  * **[Removing an Applicant](#removing-an-applicant)**
    + [Endpoint](#endpoint-3)
    + [Available methods](#available-methods-3)
    + [Query parameters](#query-parameters-3)
    + [Query formats](#query-formats)
    + [Response format](#response-format-3)

  * **[Changing an Applicant's Status](#changing-an-applicants-status)**
    + [Endpoint](#endpoint-4)
    + [Available methods](#available-methods-4)
    + [Query parameters](#query-parameters-4)
    + [Response format](#response-format-4)

  * **[Applicant's remote upload status](#applicants-remote-upload-status)**
    + [Endpoint](#endpoint-5)
    + [Available methods](#available-methods-5)
    + [Query parameters](#query-parameters-5)
    + [Query format](#query-format-1)
    + [Response formats](#response-formats)

  * **[Applicant email tracking metadata](#applicant-email-tracking-metadata)**
    + [Available headers](#available-headers)

  * **[Application Received webhook](#application-received-webhook)**

## 

This webservice allows to obtain data relating to Applicants on a given account. It can be used to list candidates and display their basic details.

## Listing Applicants
This method allows to list appropriately filtered and ordered Applicants for a given account.

### Endpoint
#### `https://ws.idibu.com/ws/rest/v1/applicants`

### Available methods
#### `GET /`
Returns all Applicants.

### Query parameters
Parameter Name | Type restrictions | Required? | Notes
-- | -- | -- | --
`hash` | **String** | **Yes** | Hash of the idibu account to which the request pertains.
`after_date` | **Date and time**<br/><br/>Format: `YYYY-MM-DD` or `YYYY-MM-DD HH:mm:ss` | No | Returns only Applicants received at or after the specified time.
`before_date` | **Date and time**<br/><br/>Format: `YYYY-MM-DD` or `YYYY-MM-DD HH:mm:ss` | No | Returns only Applicants received at or before the specified time.
`board-id` | **Integer** | No | Returns only Applicants from the Portal with the provided ID.<br/>Refer to the [Portal Management Webservice](https://github.com/oneworldmarket/idibu-api/tree/master/webservices/portal-management).
`count` | **Integer**<br/><br/>Min: 1<br/>Max: 100<br/>Default: 10 | No | Number of Applicants to return.
`job-id` | **Integer**<br/><br/>Multiple allowed, comma-separated | No | Returns only Applicants for the provided Job ID(s).<br/>Refer to the [Job Management Webservice](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/job-management/job-management-webservice.md).
`email` | **String** | No | Returns only Applicants with the given e-mail address.
`offset` | **Integer**<br/><br/>Min: 0<br/>Default: 0 | No | Numeric offset from where to start fetching Applicants (pagination).
`reference` | **String** | No | Returns only Applicants for Jobs with Reference containing the provided string.
`status` | **String** | No | Returns only Applicants that have the specified Status assigned.<br/>Use the `name` of the `status` obtainable via the [Aptrack Settings Webservice](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/settings-management/aptrack-settings.md).<br/>
`user-id` | **Integer**<br/><br/>Multiple allowed, comma-separated | No | Returns only Applicants for Jobs posted by User(s) with the provided ID(s).<br/>Refer to the [User Management Webservice](https://github.com/oneworldmarket/idibu-api/tree/master/webservices/user-management).

### Response format
```xml
<idibu generator="idibu" version="1.0">
  <response>
    <applicants>
      <applicant>
        <id>[integer]</id> <!-- applicant id -->
        <email>[string:email]</email> <!-- candidate's e-mail address -->
        <parsed_email>[string:email]</parsed_email> <!-- e-mail address parsed from the CV file -->
        <name>[string]</name> <!-- name of the candidate; will be the same as <email> if not provided or parsed -->
        <job> <!-- job for which the candidate applied; refer to https://github.com/oneworldmarket/idibu-api/blob/master/webservices/job-management -->
          <id>[integer]</id> <!-- job id -->
          <reference>[string]</reference> <!-- job reference -->
        </job>
        <portal-id>[integer]</portal-id> <!-- id of the portal on which the candidate applied; refer to https://github.com/oneworldmarket/idibu-api/tree/master/webservices/portal-management -->
        <portal-name>[string]</portal-name> <!-- name of the portal on which the candidate applied -->
        <date>[string:date]</date> <!-- when the candidate data reached the system; YYYY-MM-DD HH:mm:ss -->
        <rank>[integer]</rank> <!-- candidate's automated ranking; empty if the account does not use Aprank (currently not publicly available) -->
        <status>[string]</status> <!-- name of the candidate's status; refer to https://github.com/oneworldmarket/idibu-api/blob/master/webservices/settings-management/aptrack-settings.md -->
        <files> <!-- list of all attachments that come with the applicant - most usually just the CV -->
          <file>
            <name>[string]</name> <!-- filename of the attachment -->
            <link>[string:url]</link> <!-- direct link for the file download -->
          </file>
        </files>
      </applicant>
    </applicants>
    <total>[integer]</total> <!-- total number of applicants matching the current criteria (excluding count and offset) -->
  </response>
  <status>["success"|"failed"]</status> <!-- whether the request succeeded or not -->
</idibu>
```

---

## Applicant's detailed view
This method allows to obtain more detailed information about a particular Applicant. The response will contain similar (though not identical) data to [Listing Applicants](#listing-applicants) but with a full message as well as more details parsed from the CV file (if one is available and CV parsing is purchased as a product for the account).

### Endpoint
#### `https://ws.idibu.com/ws/rest/v1/applicants`

### Available methods
#### `GET /[id]`
Returns the detailed view of the Applicant with the provided `[id]`.

### Query parameters
Parameter Name | Type restrictions | Required? | Notes
-- | -- | -- | --
`hash` | **String** | **Yes** | Hash of the idibu account to which the request pertains.

### Response format
```xml
<idibu generator="idibu" version="1.0">
  <response>
    <id>[integer]</id> <!-- applicant id -->
    <email>[string:email]</email> <!-- candidate's e-mail address -->
    <name>[string]</name> <!-- name of the candidate; will be the same as <email> if not provided or parsed -->
    <job> <!-- job for which the candidate applied; refer to https://github.com/oneworldmarket/idibu-api/blob/master/webservices/job-management -->
      <id>[integer]</id> <!-- job id -->
      <reference>[string]</reference> <!-- job reference -->
    </job>
    <date>[string:date]</date> <!-- when the candidate data reached the system; YYYY-MM-DD HH:mm:ss -->
    <message>
      <subject>[string]</subject> <!-- message subject -->
      <html>[string]</html> <!-- message text - HTML -->
      <text>[string]</text> <!-- message text - plain -->
    </message>
    <portal> <!-- refer to https://github.com/oneworldmarket/idibu-api/tree/master/webservices/portal-management -->
      <id>[integer]</id> <!-- id of the portal on which the candidate applied -->
      <name>[string]</name> <!-- name of the portal on which the candidate applied -->
    </portal>
    <rank>[integer]</rank> <!-- candidate's automated ranking; empty if the account does not use Aprank (currently not publicly available) -->
    <status>[string]</status> <!-- name of the candidate's status; refer to https://github.com/oneworldmarket/idibu-api/blob/master/webservices/settings-management/aptrack-settings.md -->
    <files> <!-- list of all attachments that come with the applicant - most usually just the CV -->
      <file>
        <name>[string]</name> <!-- filename of the attachment -->
        <link>[string:url]</link> <!-- direct link for the file download -->
      </file>
    </files>
    <parsed> <!-- extra data parsed from the CV; only applicable if CV parsing enabled for the account; not all sections may be successfully parsed -->
      <successful>["yes"|"no"]</successful> <!-- whether the parsing process succeeded -->
      <data>[string:xml]</data> <!-- DaXtra Candidate Profile Schema; refer to https://cvxdemo.daxtra.com/cvx/#integration-output -->
      <email>[string:email]</email> <!-- e-mail address parsed from the CV file -->
      <summary>[string]</summary> <!-- candidate's summary (most usually, intro) parsed from the CV file -->
      <history>[string]</history> <!-- candidate's work history parsed from the CV file -->
      <education>[string]</education> <!-- candidate's education parsed from the CV file -->
    </parsed>
  </response>
  <status>["success"|"failed"]</status> <!-- whether the request succeeded or not -->
</idibu>
```

---

## Adding a new Applicant
This method allows to upload candidate data into the system.

**Normally, candidates arrive into the system from job boards and websites automatically after applying**. This method is meant to allow importing applicants from other sources, for example stored in the external, third party software that you are integrating with idibu.

### Endpoint
#### `https://ws.idibu.com/ws/rest/v1/applicants`

### Available methods
#### `POST /add-cv`
Creates a new Applicant in the system.

### Query parameters
Parameter Name | Type restrictions | Required? | Notes
-- | -- | -- | --
`hash` | **String** | **Yes** | Hash of the idibu account to which the request pertains.
`data` | **String** | **Yes** | The full query XML (see the [Query format](#query-format-1) below), URL-encoded within the parameter.

### Query format
```xml
<idibu>
  <job> <!-- job against which the candidate will be stored; refer to https://github.com/oneworldmarket/idibu-api/blob/master/webservices/job-management -->
    <id>[string]</id> <!-- numeric job id or url-safe-base64-encoded job id -->
    <portal>[string]</portal> <!-- id or bid of the portal that will be set as the candidate's source; refer to https://github.com/oneworldmarket/idibu-api/tree/master/webservices/portal-management -->
    <!-- if job and portal id is present, the latest post to that portal will be used -->
    <!-- if no portal id is provided, idibu CV manager (id: 1229) will be used -->
    <!-- if there are no previous postings to idibu CV manager, a new post will be created and the applicant uploaded against it -->
  </job>
  <cv> <!-- attachment that will come with the applicant, if applicable -->
    <name>[string]</name> <!-- filename of the attachment -->
    <contents>[string:base64]</contents> <-- base64-encoded file -->
  </cv>
  <email> <!-- message details -->
    <from>[string:email]</from> <!-- candidate's e-mail address -->
    <subject>[string]</subject> <!-- message subject -->
    <body>[string]</body> <!-- message text -->
  </email>
</idibu>
```

### Response format
```xml
<idibu generator="idibu" version="1.0">
  <response>[string]</response> <!-- 'CV uploaded' or an error message -->
  <status>["success"|"failed"]</status> <!-- whether the request succeeded or not -->
</idibu>
```

---

## Removing an Applicant
This method allows to delete candidate data from the system. Applicants can be removed either by their ID or their e-mail address (in which case all instances of Applicants with the address will be removed from the account).

Candidate records are queued for deletion which, in case of large amount of requests, may not be processed immediately. Due to this, the method also doesn't check for the amount or validity of the requested records, and will therefore always return successful response, even if there is nothing to remove.

Please note that once you action the removal of the candidate's data, **this process cannot be reversed in any way, under any circumstances**. This is because the data removal process fulfills our obligations as a data processor as outlined in the European Data Protection Regulation introduced in May 2018 (commonly known as GDPR). Once the candidate data is removed via this webservice, we therefore have no means of identification or retrieval of it.

**The base Applicant record will remain in the system**; all personal data, however, as well as the message and attachments, will be removed. Email address of every such deleted candidate will be changed to _deleted@idibu.com_. Such anonymized records are stored so that reporting stays accurate - refer to the [Reporting Management Webservice](https://github.com/oneworldmarket/idibu-api/tree/master/webservices/reporting-management).

### Endpoint
#### `https://ws.idibu.com/ws/rest/v1/applicants`

### Available methods
#### `POST /request-delete-by-ids`
Removes Applicants based on their ID(s) provided.

#### `POST /request-delete-by-emails`
Removes Applicants based on their e-mail address(es) provided.


### Query parameters
Parameter Name | Type restrictions | Required? | Notes
-- | -- | -- | --
`hash` | **String** | **Yes** | Hash of the idibu account to which the request pertains.
`data` | **String** | **Yes** | The full query XML (see the [Query formats](#query-formats) below), URL-encoded within the parameter.

### Query formats
#### `request-delete-by-ids`
```xml
<idibu>
  <ids>
    <id>[integer]</id> <!-- id of the Applicant to be deleted. Multiple <id> tags can be provided -->
  </ids>
</idibu>
```

#### `request-delete-by-emails`
```xml
<idibu>
  <emails>
    <email>[string:email]</email> <!-- e-mail address of the Applicant to be deleted. Multiple <email> tags can be provided -->
  </emails>
</idibu>
```

### Response format
```xml
<idibu generator="idibu" version="1.0">
  <response>
    <message>[string]</message> <!-- 'Applicants queued for deletion' or an error message -->
  </response>
  <status>["success"|"failed"]</status> <!-- whether the request succeeded or not -->
</idibu>
```

---

## Changing an Applicant's Status
This method allows to assign pre-defined Statuses to Applicants in order to manage their recruitment process as well as send automated responses to them.

Refer to the [Aptrack Settings Webservice](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/settings-management/aptrack-settings.md) for more information about how Statuses can be created and managed.

### Endpoint
#### `https://ws.idibu.com/ws/rest/v1/applicants`

### Available methods
#### `GET /[id]/set-status`
Assigns a status to the Applicant with the provided `[id]`.

### Query parameters
Parameter Name | Type restrictions | Required? | Notes
-- | -- | -- | --
`hash` | **String** | **Yes** | Hash of the idibu account to which the request pertains.
`status` | **String** | **Yes** | Name of the Status to be assigned.
`responder` | **String (enum)**<br/><br/>Default: `No`<br/><br/>Accepted values:<br/><code>No</code> - don't send the Autoresponder<br/><code>Yes</code> - send the Autoresponder | No | Whether the Autoresponder assigned to the Status (if applicable) should be sent to the candidate's e-mail address right after that Status is assigned through the request.

### Response format
```xml
<idibu generator="idibu" version="1.0">
  <response>
    <message>[string]</message> <!-- 'Status updated' or an error message -->
  </response>
  <status>["success"|"failed"]</status> <!-- whether the request succeeded or not -->
</idibu>
```

---

## Applicant's remote upload status
This method allows to set and review (store for later reference) information about the processing of candidates into an external system integrated with idibu.

Whenever obtaining Applicants from idibu into any other software - not only through the webservice but also, for example, forwarded through email - the system that ultimately processes the candidate data can call idibu webservice with information about the process. This data can be then later reviewed and investigated.

### Endpoint
#### `https://ws.idibu.com/ws/rest/v1/applicant-status`

### Available methods
#### `POST /[id]`
Saves information about the upload process of the Applicant with the provided `[id]`.

#### `GET /`
Returns information about the upload process of all Applicants.

### Query parameters
#### `POST`
Parameter Name | Type restrictions | Required? | Notes
-- | -- | -- | --
`hash` | **String** | **Yes** | Hash of the idibu account to which the request pertains.
`data` | **String** | **Yes** | The full query XML (see the [Query format](#query-format-1) below), URL-encoded within the parameter.

#### `GET`
Parameter Name | Type restrictions | Required? | Notes
-- | -- | -- | --
`hash` | **String** | **Yes** | Hash of the idibu account to which the request pertains.
`count` | **Integer**<br/><br/>Min: 1<br/>Max: 100<br/>Default: 10 | No | Number of Applicants to return.
`id` | **Integer** | No | Returns only the Applicant with the provided ID.
`offset` | **Integer**<br/><br/>Min: 0<br/>Default: 0 | No | Numeric offset from where to start fetching Applicants (pagination).
`remote-id` | **String** | No | Returns only the Applicant with the provided Remote ID.

### Query format
#### `POST`
```xml
<applicant>
  <status>["success"|"fail"]</status> <!-- whether the processing of the candidate succeeded or not in the external system -->
  <remote-id>[string]</remote-id> <!-- any string that uniquely identifies the candidate in the external system -->
  <error-message>[string]</error-message> <!-- message detailing the problem that occurred while processing the candidate data; expected on fail status -->
  <date-processed>[string:date]</date-processed> <!-- when the processing took place; the request's timestamp by default; YYYY-MM-DD HH:mm:ss -->
</applicant>
```

### Response formats
#### `POST`
```xml
<idibugenerator="idibu" version="1.0">
  <response>[string]</response> <!-- 'Applicant status saved' or an error message -->
  <status>["success"|"failed"]</status> <!-- whether the request succeeded or not -->
</idibu>
```

#### `GET`
```xml
<idibugenerator="idibu" version="1.0">
  <response>
    <applicant>
      <id>[integer]</id> <!-- applicant id -->
      <status>["success"|"fail"]</status> <!-- whether the processing of the candidate succeeded or not in the external system -->
      <remote-id>[string]</remote-id> <!-- unique identifier of the candidate in the external system -->
      <error-message>[string]</error-message> <!-- message detailing the problem that occurred while processing the candidate data; expected on fail status -->
      <date-processed>[string:date]</date-processed> <!-- when the processing took place; YYYY-MM-DD HH:mm:ss -->
      <status-info>
        <date-created>[string:date]</date-created> <!-- when the particular applicant status record was first created; YYYY-MM-DD HH:mm:ss -->
        <date-modified>[string:date]</date-modified> <!-- when the particular applicant status record was last modified; YYYY-MM-DD HH:mm:ss -->
      </status-info>
    </applicant>
  </response>
  <status>["success"|"failed"]</status> <!-- whether the request succeeded or not -->
</idibu>
```

---

## Applicant email tracking metadata
Any candidate email forwarded from idibu contains a set of custom headers with some additional metadata that can be used to to obtain additional info for your own tracking and management.

### Available headers
Header Name | Type restrictions | Notes
-- | -- | --
`X-iTrackID` | **Integer** | ID of the candidate.<br/>Refer to the [Applicant Management Webservice](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/applicant-management/applicant-management-webservice.md).
`X-iTrackID-ClientID` | **Integer** | ID of the idibu account.
`X-iTrackID-PortalID` | **Integer** | ID of the Portal from which the candidate arrived.<br/>Refer to the [Portal Management Webservice](https://github.com/oneworldmarket/idibu-api/tree/master/webservices/portal-management).
`X-iTrackID-Portal-Name` | **String** | Name of the Portal from which the candidate arrived.<br/>Refer to the [Portal Management Webservice](https://github.com/oneworldmarket/idibu-api/tree/master/webservices/portal-management).
`X-iTrackID-ClientSettingsID` | **Integer** | ID of the account's User for whose advert the candidate applied.<br/>Refer to the [User Management Webservice](https://github.com/oneworldmarket/idibu-api/tree/master/webservices/user-management).
`X-iTrackID-ClientSettings-Name` | **String** | Name and email address of the account's User for whose advert the candidate applied.<br/>Refer to the [User Management Webservice](https://github.com/oneworldmarket/idibu-api/tree/master/webservices/user-management).
`X-iTrackID-Office` | **String** | Name of the Office to which the User for whose advert the candidate applied is assigned.<br/>Refer to the [User Management Webservice](https://github.com/oneworldmarket/idibu-api/tree/master/webservices/user-management).
`X-iTrackID-Team` | **String** | Name of the Team to which the User for whose advert the candidate applied is assigned.<br/>Refer to the [User Management Webservice](https://github.com/oneworldmarket/idibu-api/tree/master/webservices/user-management).
`X-iTrackID-PostLogID` | **Integer** | ID of the Post for which the candidate applied.<br/>Refer to the [Advert Management Webservice](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/advert-management/advert-management-webservice.md).
`X-iTrackID-JobID` | **Integer** | ID of the Job for which the candidate applied.<br/>Refer to the [Job Management Webservice](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/job-management/job-management-webservice.md).
`X-iTrackID-Title` | **String** | Title of the Job for which the candidate applied.<br/>Refer to the [Job Management Webservice](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/job-management/job-management-webservice.md).
`X-iTrackID-Reference` | **String** | Reference of the Job for which the candidate applied.<br/>Refer to the [Job Management Webservice](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/job-management/job-management-webservice.md).
`X-iTrackID-Type` | **String**<br/><br/>Possible values:<br/><code>1 Contract</code><br/><code>2 Permanent</code><br/><code>4 Temporary</code> | ID and name of the Job's Type.<br/>Refer to the [Job Management Webservice](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/job-management/job-management-webservice.md).

---

## Application Received webhook
It is possible to set up a webhook which will automatically ping a pre-defined URL whenever a new candidate arrives in the system.

It is available as part of the [Webhook Management Webservice](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/webhook-management/webhook-management-webservice.md#applicationreceived).
