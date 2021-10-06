# Advert Management Webservice
  * **[Listing Adverts](#listing-adverts)**
    + [Endpoint](#endpoint)
    + [Available methods](#available-methods)
    + [Query parameters](#query-parameters)
    + [Response format](#response-format)

  * **[Advert's detailed view](#adverts-detailed-view)**
    + [Endpoint](#endpoint-1)
    + [Available methods](#available-methods-1)
    + [Query parameters](#query-parameters-1)
    + [Response format](#response-format-1)
 
 * **[Posting status](#posting-status)**
    + [Endpoint](#endpoint-2)
    + [Available methods](#available-methods-2)
    + [Query parameters](#query-parameters-2)
    + [Response format](#response-format-2)

  * **[PostLog info](#postlog-info)**
    + [Endpoint](#endpoint-3)
    + [Available methods](#available-methods-3)
    + [Query parameters](#query-parameters-3)
    + [Response format](#response-format-3)

## 

This webservice allows to obtain data relating to Advert objects of a given account.

A single [Job](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/job-management/job-management-webservice.md) object can consist of multiple Adverts, where each Advert indicates any single interaction between idibu and a posting destination (job board, website, or social media portal).

Creating Jobs and posting them as Adverts is handled through the [Posting API](https://github.com/oneworldmarket/idibu-api/tree/master/posting-api) or [Universal Posting Pages](https://github.com/oneworldmarket/idibu-api/tree/master/UPP).

## Listing Adverts
Allows to list appropriately filtered and ordered Adverts for a given account.

### Endpoint
#### `https://ws.idibu.com/ws/rest/v1/adverts/`

### Available methods
#### `GET /all`
Returns all Adverts.

#### `GET /live`
Returns all currently live Adverts - ones that are still present on their respective posting destinations.

#### `GET /archived`
Returns Adverts that are not live anymore - either automatically expired or manually deleted from their respective posting destinations.

#### `GET /[n]/days-expiring`
Returns Adverts that will expire in `[n]` days or sooner (`[n]` can be negative for Adverts that have already expired up to `[n]` days ago).

### Query parameters

Parameter Name | Type restrictions | Required? | Notes
-- | -- | -- | --
`hash` | **String** | **Yes** | Hash of the idibu account to which the request pertains.
`board` | **Integer** | No | Returns only Adverts posted to the Portal with the provided ID.<br/>Refer to the [Portal Management Webservice](https://github.com/oneworldmarket/idibu-api/tree/master/webservices/portal-management).
`count` | **Integer**<br/><br/>Min: 1<br/>Max: 100<br/>Default: 10 | No | Number of Adverts to return.
`from_date` | **Date and time**<br/><br/>Format: `YYYY-MM-DD` or `YYYY-MM-DD HH:mm:ss` | No | Returns only Adverts posted at or after the specified time.
`job-id` | **Integer**<br/><br/>Multiple allowed, comma-separated | No | Returns only Adverts posted under Job(s) with the provided ID(s).<br/>Refer to the [Job Management Webservice](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/job-management/job-management-webservice.md).
`offset` | **Integer**<br/><br/>Min: 0<br/>Default: 0 | No | Numeric offset from where to start fetching Adverts (pagination).
`order` | **String (enum)**<br/><br/>Default: `date-desc`<br/><br/>Accepted values:<br/><code>date-desc</code> - Date Posted (desc)<br/><code>date-asc</code> - Date Posted (asc)<br/><code>title-asc</code> - By Title (asc)<br/><code>title-desc</code> - By Title (desc) | No | How the Adverts should be ordered in the response.
`reference` | **String** | No | Returns only Adverts with Reference containing the provided string.
`sender` | **Integer**<br/><br/>Multiple allowed, comma-separated | No | Returns only Adverts belonging to User(s) with the provided ID(s).<br/>Refer to the [User Management Webservice](https://github.com/oneworldmarket/idibu-api/tree/master/webservices/user-management).
`title` | **String** | No | Returns only Adverts with Title containing the provided string.
`title-or-reference` | **String** | No | Returns only Adverts with Reference or Title containing the provided string.
`to_date` | **Date and time**<br/><br/>Format: `YYYY-MM-DD` or `YYYY-MM-DD HH:mm:ss` | No | Returns only Adverts posted at or before the specified time.

### Response format
```xml
<idibu generator="idibu" version="1.0">
  <response>
    <adverts>
      <advert>
        <id>[integer]</id> <!-- advert id -->
        <delete_log>[integer]</delete_log> <!-- indicates if the advert has been deleted (1) or not (0) -->
        <creation_date>[string:date]</creation_date> <!-- advert's creation date; YYYY-MM-DD HH:mm:ss -->
        <expiry_date>[string:date]</expiry_date> <!-- date the advert expires or was deleted; YYYY-MM-DD HH:mm:ss -->
        <sender> <!-- refer to https://github.com/oneworldmarket/idibu-api/tree/master/webservices/user-management -->
          <id>[integer]</id> <!-- sender's profile id -->
          <firstname>[string]</firstname> <!-- sender's first name -->
          <lastname>[string]</lastname> <!-- sender's last name -->
          <email>[string:email]</email> <!-- sender's email -->
        </sender>
        <job> <!-- refer to https://github.com/oneworldmarket/idibu-api/blob/master/webservices/job-management -->
          <id>[integer]</id> <!-- job id -->
          <title>[string]</title> <!-- job title -->
          <reference>[string]</reference> <!-- job reference -->
        </job>
        <aptrack> <!-- refer to https://github.com/oneworldmarket/idibu-api/tree/master/webservices/applicant-management -->
          <total>[integer]</total> <!-- total applications for the job -->
          <unread>[integer]</unread> <!-- total unread applications for the job -->
        </aptrack>
        <posting> <!-- number of various types of posts for the given advert -->
          <success>[integer]</success> <!-- successfully posted -->
          <update>[integer]</update> <!-- successfully posted and updated -->
          <fail>[integer]</fail> <!-- not posted successfully -->
          <pending>[integer]</pending> <!-- not posted yet - waiting in the posting queue -->
          <delete>[integer]</delete> <!-- successfully deleted -->
        </posting>
      </advert>
    </adverts>
    <total>[integer]</total> <!-- total number of ads matching the current criteria (excluding count and offset)
  </response>
  <status>["success"|"failed"]</status> <!-- whether the request succeeded or not -->
</idibu>
```

---

## Advert's detailed view
Allows to obtain more detailed information about a particular Advert. The response format is the same as for [Listing Adverts](#listing-adverts) but more `job` and `posting` data is provided.

### Endpoint
#### `https://ws.idibu.com/ws/rest/v1/adverts/`

### Available methods
#### `GET /[id]`
Returns the detailed view of the Advert with the provided `[id]`.

### Query parameters
Parameter Name | Type restrictions | Required? | Notes
-- | -- | -- | --
`hash` | **String** | **Yes** | Hash of the idibu account to which the request pertains.

### Response format
```xml
<idibu generator="idibu" version="1.0">
  <response>
    <advert>
      <id>[integer]</id> <!-- advert id -->
      <delete_log>[integer]</delete_log> <!-- indicates if the advert has been deleted (1) or not (0) -->
      <creation_date>[string:date]</creation_date> <!-- advert's creation date; YYYY-MM-DD HH:mm:ss -->
      <expiry_date>[string:date]</expiry_date> <!-- date the advert expires or was deleted; YYYY-MM-DD HH:mm:ss -->
      <sender> <!-- refer to https://github.com/oneworldmarket/idibu-api/tree/master/webservices/user-management -->
        <id>[integer]</id> <!-- sender's profile id -->
        <firstname>[string]</firstname> <!-- sender's first name -->
        <lastname>[string]</lastname> <!-- sender's last name -->
        <email>[string:email]</email> <!-- sender's email -->
      </sender>
      <job> <!-- refer to https://github.com/oneworldmarket/idibu-api/blob/master/webservices/job-management -->
        <id>[integer]</id> <!-- job id -->
        <title>[string]</title> <!-- job title -->
        <reference>[string]</reference> <!-- job reference -->
        <description>[string]</description> <!-- job description -->
        <sector id="[integer]">[string]</sector> <!-- sector id and name -->
        <location id="[integer]" code="[string]">[string]</location> <!-- country id, code and name -->
        <sub_location id="[integer]">[string]</sub_location> <!-- location id and place_name -->
        <!-- for the three above, refer to https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/Sector-and-locations.md -->
        <type id="[1|2|4]">[Contract|Permanent|Temporary]</type> <!-- job type -->
        <duration>[string]</duration> <!-- duration of the job (how long the candidate would work) -->
        <salary_minimum>[string]</salary_minimum> <!-- minimum salary, can contain decimal points -->
        <salary_maximum>[string]</salary_maximum> <!-- maximum salary, can contain decimal points -->
        <salary_per>["annum"|"month"|"week"|"day"|"hour"]</salary_per> <!-- salary period -->
        <salary_currency>[string]</salary_currency> <!-- three-letter ISO code -->
        <salary_extras>[string]</salary_extras> <!-- additional benefits -->
        <salary_override>[string]</salary_override> <!-- if present, usually replaces all other salary information -->
        <application_url>[string]</application_url> <!-- external application url -->
        <start_date>[string:date]</start_date> <!-- when the candidate would start working; YYYY-MM-DD HH:mm:ss -->
      </job>
      <aptrack> <!-- refer to https://github.com/oneworldmarket/idibu-api/tree/master/webservices/applicant-management -->
        <total>[integer]</total> <!-- total applications for the job -->
        <unread>[integer]</unread> <!-- total unread applications for the job -->
      </aptrack>
      <posting> <!-- number of various types of posts for the given advert -->
        <success>[integer]</success> <!-- successfully posted -->
        <update>[integer]</update> <!-- successfully posted and updated -->
        <fail>[integer]</fail> <!-- not posted successfully -->
        <pending>[integer]</pending> <!-- not posted yet - waiting in the posting queue -->
        <delete>[integer]</delete> <!-- successfully deleted -->
        <details> <!-- not present if the advert wasn't posted to any portal -->
          <detail> <!-- can be multiple - each detail object relates to one of the posts which total numbers are counted above -->
            <portal> <!-- portal to which the advert was posted; refer to https://github.com/oneworldmarket/idibu-api/tree/master/webservices/portal-management -->
              <id>[integer]</id> <!-- portal id -->
              <url>[string:url]</url> <!-- website's URL -->
              <logo>[string]</logo> <!-- name of the image file - portal's logo - that sits under https://uk.idibu.com/images/stories/Portal_logos/ -->
              <name>[string]</name> <!-- portal name -->
            </portal>
            <post>
              <id>[integer]</id> <!-- PostLog id -->
              <start>[string:date]</start> <!-- posting date; YYYY-MM-DD HH:mm:ss -->
              <stop>[string:date]</stop> <!-- intended expiry date; YYYY-MM-DD HH:mm:ss -->
              <type>["post"|"update"|"delete"]</type> <!-- whether the posting was a new post, an update of an existing job, or a delete request -->
              <status>["success"|"failed"]</status> <!-- whether the posting succeeded or not -->
              <deletable>["yes"|"no"]</deletable> <!-- whether the post can be deleted -->
            </post>
            <expired>["yes"|"no"]</expired> <!-- whether the post is already expired -->
            <applicants>[integer]</applicants> <!-- applicant count for this post -->
            <link>[string:url]</link> <!-- URL of the posting on the portal (if supported by the portal) -->
          </detail>
        </details>
      </posting>
    </advert>
  </response>
  <status>["success"|"failed"]</status> <!-- whether the request succeeded or not -->
</idibu>
```

---

## Posting status
Allows to obtain the Advert's posting status - detailed information about the successful posting or details of the error.

### Endpoint
#### `https://ws.idibu.com/ws/rest/v1/adverts/`

### Available methods
#### `GET /posting`
Returns the status of the posting.

### Query parameters
Parameter Name | Type restrictions | Required? | Notes
-- | -- | -- | --
`hash` | **String** | **Yes** | Hash of the idibu account to which the request pertains.
`pq-id` | **Integer** | **Yes** | `QUEUEID` of the posting.<br/>Refer to the [Response Messages](https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/sub-and-resp.md#response-messages) section of the Posting API.

### Response format
```xml
<idibu generator="idibu" version="1.0">
  <response> <!-- empty response indicates no posts for the given pq-id; this can happen if the postings have been canceled before leaving the queue -->
    <portal> <!-- portal to which the advert was posted; refer to https://github.com/oneworldmarket/idibu-api/tree/master/webservices/portal-management -->
      <id>[integer]</id> <!-- portal id -->
      <url>[string:url]</url> <!-- website's URL -->
      <logo>[string]</logo> <!-- name of the image file - portal's logo - that sits under https://uk.idibu.com/images/stories/Portal_logos/ -->
      <name>[string]</name> <!-- portal name -->
    </portal>
    <post> <!-- if the posting succeeded, post's details will be here -->
      <start>[string:date]</start> <!-- posting date; YYYY-MM-DD HH:mm:ss -->
      <stop>[string:date]</stop> <!-- intended expiry date; YYYY-MM-DD HH:mm:ss -->
      <type>["post"|"update"|"delete"]</type> <!-- whether the posting was a new post, an update of an existing job, or a delete request -->
      <status>["success"|"failed"]</status> <!-- whether the posting succeeded or not -->
      <deletable>["yes"|"no"]</deletable> <!-- whether the post can be deleted -->
    </post>
    <errordetails> <!-- if the posting failed, error details will be here -->
      <errordetail>
        <description>[string]</description> <!-- a user-friendly description of what caused the posting to fail -->
        <solution>[string]</solution> <!-- if the error is known - a user-friendly description of how to resolve the issue -->
        <reasons>[string]</reasons> <!-- if the error is unknown - a generic user-friendly message -->
      </errordetail>
    </errordetails>
    <expired>["yes"|"no"]</expired> <!-- whether the post is expired -->
    <applicants>[integer]</applicants> <!-- applicant count for this post -->
    <link>[string:url]</link> <!-- URL of the posting on the portal (if supported by the portal) -->
  </response>
  <status>["success"|"failed"]</status> <!-- whether the request succeeded or not -->
</idibu>
```

---

## PostLog info
Allows to obtain the Advert's posting log - technical information about the posting process, including the data that was sent to the posting destination and the output returned.<br/>**This data should be for internal use only** (i.e. contacting idibu in order to debug further); sometimes, the data is sent to internal scripts before interacting with the target website, so it might bear no context or value even for the job board in question.

### Endpoint
#### `https://ws.idibu.com/ws/rest/v1/posting-logs/`

### Available methods
#### `GET /[id]`
Returns the detailed view of the PostLog with the provided `[id]`.
PostLog's `[id]` is obtainable from the [Advert's detailed view](#adverts-detailed-view) as `post/id`. 

### Query parameters
Parameter Name | Type restrictions | Required? | Notes
-- | -- | -- | --
`hash` | **String** | **Yes** | Hash of the idibu account to which the request pertains.

### Response format
```xml
<idibu generator="idibu" version="1.0">
  <response>
    <log> <!-- logs are stored for about three months; please be advised that some requests are sent to (and responses generated by) internal endpoints so the data may not always represent the actual interaction with a job board or website -->
      <id>[integer]</id> <!-- PostLog id -->
      <portal>[integer]</portal> <!-- portal to which the advert was posted; refer to https://github.com/oneworldmarket/idibu-api/tree/master/webservices/portal-management -->
      <type>["success"|"update"|"fail"|"deleted"|"pending"]</type> <!-- status on the portal -->
      <created>[string:date]</created> <!-- when the job exactly posted and generated the response; YYYY-MM-DD HH:mm:ss -->
      <job> <!-- refer to https://github.com/oneworldmarket/idibu-api/blob/master/webservices/job-management -->
        <id>[integer]</id> <!-- job id -->
        <title>[string]</title> <!-- job title -->
        <reference>[string]</reference> <!-- job reference -->
      </job>
      <request>[string]</request> <!-- body of the request that was sent to the portal's endpoint -->
      <response>[string]</response> <!-- body of the response that was returned by the portal -->
    </log>
  </response>
  <status>["success"|"failed"]</status> <!-- whether the request succeeded or not -->
</idibu>
```
