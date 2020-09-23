# Job Management Webservice
  * **[Listing Jobs](#listing-jobs)**
    + [Endpoint](#endpoint)
    + [Available methods](#available-methods)
    + [Query parameters](#query-parameters)
    + [Response format](#response-format)

  * **[Job's detailed view](#jobs-detailed-view)**
    + [Endpoint](#endpoint-1)
    + [Available methods](#available-methods-1)
    + [Query parameters](#query-parameters-1)
    + [Response format](#response-format-1)

## 

This webservice allows to obtain data relating to Job objects of a given account. It can be used to list jobs same as [Ad Manager](https://v3-docs.idibu.com/article/776-ad-manager-2-0-intro-and-overview) in idibu.

A single Job object can consist of multiple [Adverts](https://github.com/oneworldmarket/idibu-api/tree/master/webservices/advert-management), where each Advert indicates any single interaction between idibu and a posting destination (job board, website, or social media portal).

Creating Jobs and posting them as Adverts is handled through the [Posting API](https://github.com/oneworldmarket/idibu-api/tree/master/posting-api) or [Universal Posting Pages](https://github.com/oneworldmarket/idibu-api/tree/master/UPP).

## Listing Jobs
This method allows to list appropriately filtered and ordered Jobs for a given account.

### Endpoint
#### `https://ws.idibu.com/ws/rest/v1/jobs`

### Available methods
#### `GET /all`
Returns all Jobs.

#### `GET /live`
Returns all currently live Jobs - with Adverts still present on their respective posting destinations.

#### `GET /archived`
Returns Jobs that are not live anymore - with Adverts either automatically expired or manually deleted from their respective posting destinations.

#### `GET /[n]/days-expiring`
Returns Jobs that will expire in `[n]` days or sooner (`[n]` can be negative for Jobs that have already expired up to `[n]` days ago).

### Query parameters
Parameter Name | Type restrictions | Required? | Notes
-- | -- | -- | --
`hash` | **String** | **Yes** | Hash of the idibu account to which the request pertains.
`count` | **Integer**<br/><br/>Min: 1<br/>Max: 100<br/>Default: 10 | No | Number of Jobs to return.
`offset` | **Integer**<br/><br/>Min: 0<br/>Default: 0 | No | Numeric offset from where to start fetching Jobs.
`order` | **String (enum)**<br/><br/>Default: `update-desc`<br/><br/>Accepted values:<br/><code>update-desc</code> - Last Posted<br/><code>update-asc</code> - First Posted<br/><code>date-desc</code> - Date Added (desc)<br/><code>date-asc</code> - Date Added (asc)<br/><code>title-asc</code> - By Title (asc)<br/><code>title-desc</code> - By Title (desc) | No | How the Jobs should be ordered in the response.<br/>Consult [this article](https://v2-docs.idibu.com/article/106-admanager-view-order-options) for more info.
`reference` | **String** | No | Returns only Jobs with Reference containing the provided string.
`sender` | **Integer** | No | Returns only Jobs belonging to the User with the provided ID.<br/>Refer to the [User Management Webservice](https://github.com/oneworldmarket/idibu-api/tree/master/webservices/user-management).
`title` | **String** | No | Returns only Jobs with Title containing the provided string.
`title-or-reference` | **String** | No | Returns only Jobs with Reference or Title containing the provided string.

### Response format
```xml
<idibu generator="idibu" version="1.0">
  <response>
    <jobs>
      <job>
        <id>[integer]</id> <!-- job id -->
        <reference>[string]</reference> <!-- job reference -->
        <title>[string]</title> <!-- job title -->
        <sender> <!-- refer to https://github.com/oneworldmarket/idibu-api/tree/master/webservices/user-management -->
          <id>[integer]</id> <!-- sender's profile id -->
          <firstname>[string]</firstname> <!-- sender's first name -->
          <lastname>[string]</lastname> <!-- sender's last name -->
          <email>[string:email]</email> <!-- sender's email -->
        </sender>
        <sector id="[integer]">[string]</sector> <!-- sector id and name -->
        <location id="[integer]" code="[string]">[string]</location> <!-- country id, code and name -->
        <sub_location id="[integer]">[string]</sub_location> <!-- location id and place_name -->
        <!-- For the three above, refer to https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/Sector-and-locations.md -->
        <type id="[1|2|4]">[Contract|Permanent|Temporary]</type> <!-- job type -->
        <working_hours>[Full Time|Part Time]</working_hours> <!-- working hours -->
        <duration>[string]</duration> <!-- duration of the job (how long the candidate would work) -->
        <salary> <!-- salary info -->
          <minimum>[string]</minimum> <!-- minimum salary, can contain decimal points -->
          <maximum>[string]</maximum> <!-- maximum salary, can contain decimal points -->
          <currency>[string]</currency> <!-- three-letter ISO code -->
          <per>["annum"|"month"|"week"|"day"|"hour"]</per> <!-- salary period -->
          <extras>[string]</extras> <!-- additional benefits -->
          <override>[string]</override> <!-- if present, usually replaces all other salary information -->
        </salary>
        <application_url>[string]</application_url> <!-- external application url -->
        <creation_date>[string:date]</creation_date> <!-- job's creation date; YYYY-MM-DD HH:mm:ss -->
        <update_date>[string:date]</update_date> <!-- last posting date; YYYY-MM-DD HH:mm:ss -->
        <start_date>[string:date]</start_date> <!-- first posting date; YYYY-MM-DD HH:mm:ss -->
        <expiry_date>[string:date]</expiry_date> <!-- date the job expires or was deleted; YYYY-MM-DD HH:mm:ss -->
        <aptrack> <!-- refer to https://github.com/oneworldmarket/idibu-api/tree/master/webservices/applicant-management -->
          <total>[integer]</total> <!-- total applications for the job -->
          <unread>[integer]</unread> <!-- total unread applications for the job -->
        </aptrack>
        <latest_advert> <!-- data on the last advert object; refer to https://github.com/oneworldmarket/idibu-api/tree/master/webservices/advert-management -->
          <id>[integer]</id> <!-- advert id -->
          <creation_date>[string:date]</creation_date> <!-- advert's creation date; YYYY-MM-DD HH:mm:ss -->
        </latest_advert>
        <portals>
          <!-- job status on each portal -->
          <portal> <!-- the posting destination -->
            <id>[integer]</id> <!-- portal id -->
            <name>[string]</name> <!-- portal name -->
            <status>["live"|"expired"|"failed"|"deleted"|"pending"]</status> <!-- status on the portal -->
            <deletable>["true"|"false"]</deletable> <!-- whether the post can be deleted -->
            <pending>["true"|"false"]</pending> <!-- whether there are pending posts on the portal -->
            <error>["true"|"false"]</error> <!-- whether the last posting attempt resulted in error -->
            <warning>["true"|"false"]</warning> <!-- whether the last posting attempt had warnings -->
            <expiry>[string:date]</expiry> <!-- current expiry or deletion date on the portal; YYYY-MM-DD HH:mm:ss -->
            <last_update>[string:date]</last_update> <!-- date of last posting on the portal; YYYY-MM-DD HH:mm:ss -->
            <last_posting_id>[integer]</last_posting_id> <!-- last posting (PostLog) id -->
            <applicants>[integer]</applicants> <!-- applicant count on the portal -->
          </portal>
        </portals>
      </job>
    </jobs>
    <total>[integer]</total> <!-- total number of jobs matching the current criteria (excluding count and offset) -->
  </response>
  <status>["success"|"failed"]</status> <!-- whether the request succeeded or not -->
</idibu>
```

---

## Job's detailed view
This method allows to obtain more detailed information about a particular Job. The response format is the same as for [Listing Jobs](#listing-jobs) but `description` and a list of `postings` are added.

### Endpoint
#### `https://ws.idibu.com/ws/rest/v1/jobs`

### Available methods
#### `GET /[id]`
Returns the detailed view of the Job with the provided `[id]`.

### Query parameters
Parameter Name | Type restrictions | Required? | Notes
-- | -- | -- | --
`hash` | **String** | **Yes** | Hash of the idibu account to which the request pertains.

### Response format
```xml
<idibu generator="idibu" version="1.0">
  <response>
    <job>
      <id>[integer]</id> <!-- job id -->
      <reference>[string]</reference> <!-- job reference -->
      <title>[string]</title> <!-- job title -->
      <description>[string]</description><!-- job description (detail view only) -->
      <sender> <!-- refer to https://github.com/oneworldmarket/idibu-api/tree/master/webservices/user-management -->
        <id>[integer]</id> <!-- sender's profile id -->
        <firstname>[string]</firstname> <!-- sender's first name -->
        <lastname>[string]</lastname> <!-- sender's last name -->
        <email>[string:email]</email> <!-- sender's email -->
      </sender>
      <sector id="[integer]">[string]</sector> <!-- sector id and name -->
      <location id="[integer]" code="[string]">[string]</location> <!-- country id, code and name -->
      <sub_location id="[integer]">[string]</sub_location> <!-- location id and place_name -->
      <!-- for the three above, refer to https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/Sector-and-locations.md -->
      <type id="[1|2|4]">[Contract|Permanent|Temporary]</type> <!-- job type -->
      <working_hours>[Full Time|Part Time]</working_hours> <!-- working hours -->
      <duration>[string]</duration> <!-- duration of the job (how long the candidate would work) -->
      <salary> <!-- salary info -->
        <minimum>[string]</minimum> <!-- minimum salary, can contain decimal points -->
        <maximum>[string]</maximum> <!-- maximum salary, can contain decimal points -->
        <currency>[string]</currency> <!-- three-letter ISO code -->
        <per>["annum"|"month"|"week"|"day"|"hour"]</per> <!-- salary period -->
        <extras>[string]</extras> <!-- additional benefits -->
        <override>[string]</override> <!-- if present, usually replaces all other salary information -->
      </salary>
      <application_url>[string]</application_url> <!-- external application url -->
      <creation_date>[string:date]</creation_date> <!-- job's creation date; YYYY-MM-DD HH:mm:ss -->
      <update_date>[string:date]</update_date> <!-- last posting date; YYYY-MM-DD HH:mm:ss -->
      <start_date>[string:date]</start_date> <!-- first posting date; YYYY-MM-DD HH:mm:ss -->
      <expiry_date>[string:date]</expiry_date> <!-- date the job expires or was deleted; YYYY-MM-DD HH:mm:ss -->
      <aptrack> <!-- refer to https://github.com/oneworldmarket/idibu-api/tree/master/webservices/applicant-management -->
        <total>[integer]</total> <!-- total applications for the job -->
        <unread>[integer]</unread> <!-- total unread applications for the job -->
      </aptrack>
       <latest_advert> <!-- data on the last advert object; refer to https://github.com/oneworldmarket/idibu-api/tree/master/webservices/advert-management -->
          <id>[integer]</id> <!-- advert id -->
          <creation_date>[string:date]</creation_date> <!-- advert's creation date; YYYY-MM-DD HH:mm:ss -->
        </latest_advert>
      <portals>
        <!-- job status on each portal -->
        <portal> <!-- the posting destination -->
          <id>[integer]</id> <!-- portal id -->
          <name>[string]</name> <!-- portal name -->
          <status>["live"|"expired"|"failed"|"deleted"|"pending"]</status> <!-- status on the portal -->
          <deletable>["true"|"false"]</deletable> <!-- whether the post can be deleted -->
          <pending>["true"|"false"]</pending> <!-- whether there are pending posts on the portal -->
          <error>["true"|"false"]</error> <!-- whether the last posting attempt resulted in error -->
          <warning>["true"|"false"]</warning> <!-- whether the last posting attempt had warnings -->
          <expiry>[string:date]</expiry> <!-- current expiry or deletion date on the portal; YYYY-MM-DD HH:mm:ss -->
          <last_update>[string:date]</last_update> <!-- date of last posting on the portal; YYYY-MM-DD HH:mm:ss -->
          <last_posting_id>[integer]</last_posting_id> <!-- last posting (PostLog) id -->
          <applicants>[integer]</applicants> <!-- applicant count on the portal -->
        </portal>
      </portals>
      <postings>
        <!-- detailed list of postings (PostLogs) - only in detail view -->
        <posting>
          <id>[integer]</id> <!-- PostLog id -->
          <date>[string:date]</date> <!-- posting date; YYYY-MM-DD HH:mm:ss -->
          <portal>[integer]</portal> <!-- portal id -->
          <start_post>2019-04-18 16:11:08</start_post> <!-- posting date; YYYY-MM-DD HH:mm:ss -->
          <stop_post>2019-05-16 23:59:00</stop_post> <!-- intended expiry date; YYYY-MM-DD HH:mm:ss -->
          <status>["posted"|"updated"|"deleted"|"failed"]</status> <!-- posting status -->
          <link>[string]</link> <!-- URL of the posting on the portal (if supported by the portal) -->
        </posting>
      </postings>
    </job>
  </response>
  <status>["success"|"failed"]</status> <!-- whether the request succeeded or not -->
</idibu>
```
