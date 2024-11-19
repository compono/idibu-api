# Webhook Management Webservice
  * **[Creating or updating a webhook subscription](#creating-or-updating-a-webhook-subscription)**
    + [Endpoint](#endpoint)
    + [Available methods](#available-methods)
    + [Query parameters](#query-parameters)
    + [Query format](#query-format)
    + [Response format](#response-format)
  * **[Listing webhook subscriptions](#listing-webhook-subscriptions)**
    + [Endpoint](#endpoint-1)
    + [Available methods](#available-methods-1)
    + [Query parameters](#query-parameters-1)
    + [Response format](#response-format-1)
  * **[Deleting a webhook subscription](#deleting-a-webhook-subscription)**
    + [Endpoint](#endpoint-2)
    + [Available methods](#available-methods-2)
    + [Query parameters](#query-parameters-2)
    + [Response format](#response-format-2)
  * **[Available webhook types](#available-webhook-types)**
    + [`ApplicationReceivedV2`](#applicationreceivedv2)
    + [`JobCreated`](#jobcreated)
    + [`PostAdded`](#postadded)
    + [`PostDeleted`](#postdeleted)
    + [`PostFailed`](#postfailed)
    + [`PostUpdated`](#postupdated)
* **[Webhook requests](#webhook-requests)**

## 

This webservice allows you to create, list, and delete webhook subscriptions for various types of events that occur in the system.

For any account, any number of subscriptions, for any combination of events can be created, and different URLs specified for the callbacks, with an option to sign the payload for authorization.

The format of the data that idibu sends as part of the events is standardized and it is up to you to receive, process, and understand that data through further use of other related webservices.

All requests are queued and, depending on current traffic, may not arrive immediately.

## Creating or updating a webhook subscription
This method allows you to subscribe to any type of webhooks available in the system.

The `url` specified as part of the subscription is the one that the system will send HTTP requests to whenever the specified event types occur. It also uniquely identifies the webhook - performing the call with the same `url` will update an existing subscription.

The optional `secret` parameter (used to authenticate the requests) will _not_ be returned as part of the [Listing webhook subscriptions](#listing-webhook-subscriptions) method and therefore needs to be managed externally.

### Endpoint
#### `https://ws.idibu.com/ws/rest/v1/webhooks`

### Available methods
#### `POST /`
Sets up a subscription for events specified in the data.

### Query parameters
Parameter Name | Type restrictions | Required? | Notes
-- | -- | -- | --
`hash` | **String** | **Yes** | Hash of the idibu account to which the request pertains.
`data` | **String** | **Yes** | The full query XML (see the [Query format](#query-format) below), URL-encoded within the parameter.

### Query format
```xml
<subscription>
  <url>[string:url]</url> <!-- URL to which the data will be sent whenever the event(s) occur(s); uniquely identifies the webhook -->
  <types>[string]</types> <!-- comma-separated list of event types; see "Available webhook types" below -->
  <secret>[string]</secret> <!-- optional; will be used to sign the webhook HTTP request body using HMAC-SHA256 algorithm with the bytes of the provided 'secret' as a key. The resulting hash is put in the 'authorization' header of the webhook HTTP request. -->
</subscription>
```

### Response format
```xml
<idibugenerator="idibu" version="1.0">
  <response>[string]</response> <!-- 'Subscription created.' for a new <url> or 'Subscription updated.' for an existing <url>; or an error <message> -->
  <status>["success"|"failed"]</status> <!-- whether the request succeeded or not -->
</idibu>
```

---

## Listing webhook subscriptions
This method allows to list all the webhooks the account is currently subscribed to.

The `secret` parameter (used to authenticate the requests) which can be optionally defined while [Creating or updating a webhook subscription](#creating-or-updating-a-webhook-subscription) will _not_ be returned as part of this call.

### Endpoint
#### `https://ws.idibu.com/ws/rest/v1/webhooks`

### Available methods
#### `GET /`
Lists all webhooks to which the account is currently subscribed.

### Query parameters
Parameter Name | Type restrictions | Required? | Notes
-- | -- | -- | --
`hash` | **String** | **Yes** | Hash of the idibu account to which the request pertains.

### Response format
```xml
<idibugenerator="idibu" version="1.0">
  <response>
    <subscriptions>
      <subscription> <!-- can be multiple -->
        <url>[string:url]</url> <!-- URL to which the data will be sent whenever the event(s) occur(s); uniquely identifies the webhook -->
        <types>[string]</types> <!-- comma-separated list of event types; see "Available webhook types" below -->
        <modified>[string:date]</modified> <!-- last modification date; YYYY-MM-DD HH:mm:ss -->
      </subscription>
    </subscriptions>
  </response>
  <status>["success"|"failed"]</status> <!-- whether the request succeeded or not -->
</idibu>
```

---

## Deleting a webhook subscription
This method allows you to remove an existing webhook subscription.

### Endpoint
#### `https://ws.idibu.com/ws/rest/v1/webhooks`

### Available methods
#### `DELETE /[url]`
Removes the webhook with the provided `[url]`. Please make sure to url-encode the `[url]`.

### Query parameters
Parameter Name | Type restrictions | Required? | Notes
-- | -- | -- | --
`hash` | **String** | **Yes** | Hash of the idibu account to which the request pertains.

### Response format
```xml
<idibugenerator="idibu" version="1.0">
  <response>[string]</response> <!-- 'Subscription deleted.' or an error <message> -->
  <status>["success"|"failed"]</status> <!-- whether the request succeeded or not -->
</idibu>
```

---

## Available webhook types
Below is the list of all currently available event types, with their descripton and details of the HTTP request they would generate.

### `ApplicationReceivedV2`
Triggered whenever a new candidate arrives on the account.

The following parameters will be passed in the body of the request:

Parameter Name | Type restrictions | Notes
-- | -- | --
`event_id` | **GUID** | ID of the event in idibu's database; please provide it when contacting support.
`type` | **String** | `ApplicationReceived`
`client_id` | **Integer** | ID of the idibu account.
`sender_id` | **Integer** | ID of the account's User for whose advert the candidate applied.<br/>Refer to the [User Management Webservice](https://github.com/oneworldmarket/idibu-api/tree/master/webservices/user-management).
`job_id` | **Integer** | ID of the Job for which the candidate applied.<br/>Refer to the [Job Management Webservice](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/job-management/job-management-webservice.md).
`job_reference` | **String** | Reference of the Job for which the candidate applied.<br/>Refer to the [Job Management Webservice](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/job-management/job-management-webservice.md).
`job_title` | **String** | Title of the Job for which the candidate applied.<br/>Refer to the [Job Management Webservice](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/job-management/job-management-webservice.md).
`postlog_id` | **Integer** | ID of the Post for which the candidate applied.<br/>Refer to the [Advert Management Webservice](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/advert-management/advert-management-webservice.md).
`aptrack_id` | **Integer** | ID of the candidate.<br/>Refer to the [Applicant Management Webservice](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/applicant-management/applicant-management-webservice.md).
`from` | **String (email)** | Candidate's email address.
`portal_id` | **Integer** | ID of the Portal from which the candidate arrived.<br/>Refer to the [Portal Management Webservice](https://github.com/oneworldmarket/idibu-api/tree/master/webservices/portal-management).
`date` | **Date and time**<br/><br/>Format: `YYYY-MM-DD HH:mm:ss` | The moment of the candidate reaching idibu system.

### `JobCreated`
Triggered whenever a new Job is created on the account. Please note that a 'job' object is not the same as a 'vacancy' used in the idibu V3 system. See [here](https://github.com/oneworldmarket/idibu-api/tree/master/webservices/job-management) for more details.

The following parameters will be passed in the body of the request:

Parameter Name | Type restrictions | Notes
-- | -- | --
`event_id` | **GUID** | ID of the event in idibu's database; please provide it when contacting support.
`type` | **String** | `JobCreated`
`client_id` | **Integer** | ID of the idibu account.
`sender_id` | **Integer** | ID of the account's User that created the Job.<br/>Refer to the [User Management Webservice](https://github.com/oneworldmarket/idibu-api/tree/master/webservices/user-management).
`job_id` | **Integer** | ID of the Job.<br/>Refer to the [Job Management Webservice](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/job-management/job-management-webservice.md).
`job_reference` | **String** | Reference of the Job.<br/>Refer to the [Job Management Webservice](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/job-management/job-management-webservice.md).
`job_title` | **String** | Title of the Job.<br/>Refer to the [Job Management Webservice](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/job-management/job-management-webservice.md).
`date` | **Date and time**<br/><br/>Format: `YYYY-MM-DD HH:mm:ss` | The moment of the Job's creation.

### `PostAdded`
Triggered whenever a _successful posting_ leaves the posting queue.

Please keep in mind that whether the Post is a _succcessful posting_, _successful update_, or _unsuccessful posting_ is not pre-defined and depends on the response that idibu receives from the given Portal (posting destination) after the posting attempt.

The following parameters will be passed in the body of the request:

Parameter Name | Type restrictions | Notes
-- | -- | --
`event_id` | **GUID** | ID of the event in idibu's database; please provide it when contacting support.
`type` | **String** | `PostAdded`
`client_id` | **Integer** | ID of the idibu account.
`sender_id` | **Integer** | ID of the account's User that posted the ad.<br/>Refer to the [User Management Webservice](https://github.com/oneworldmarket/idibu-api/tree/master/webservices/user-management).
`job_id` | **Integer** | ID of the Job.<br/>Refer to the [Job Management Webservice](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/job-management/job-management-webservice.md).
`job_reference` | **String** | Reference of the Job.<br/>Refer to the [Job Management Webservice](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/job-management/job-management-webservice.md).
`job_title` | **String** | Title of the Job.<br/>Refer to the [Job Management Webservice](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/job-management/job-management-webservice.md).
`advert_id` | **Integer** | ID of the Advert.<br/>Refer to the [Advert Management Webservice](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/advert-management/advert-management-webservice.md).
`postlog_id` | **Integer** | ID of the Post.<br/>Refer to the [Advert Management Webservice](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/advert-management/advert-management-webservice.md).
`portal_id` | **Integer** | ID of the Portal to which the Post was sent.<br/>Refer to the [Portal Management Webservice](https://github.com/oneworldmarket/idibu-api/tree/master/webservices/portal-management).
`date` | **Date and time**<br/><br/>Format: `YYYY-MM-DD HH:mm:ss` | The moment of the Post reaching the Portal.

### `PostDeleted`
Triggered whenever a _successful deletion_ leaves the posting queue.

Please keep in mind that whether the Post is a _succcessful deletion_ or _unsuccessful deletion_ is not pre-defined and depends on the response that idibu receives from the given Portal (posting destination) after the deletion attempt.

The following parameters will be passed in the body of the request:

Parameter Name | Type restrictions | Notes
-- | -- | --
`event_id` | **GUID** | ID of the event in idibu's database; please provide it when contacting support.
`type` | **String** | `PostDeleted`
`client_id` | **Integer** | ID of the idibu account.
`sender_id` | **Integer** | ID of the account's User that posted the ad.<br/>Refer to the [User Management Webservice](https://github.com/oneworldmarket/idibu-api/tree/master/webservices/user-management).
`job_id` | **Integer** | ID of the Job.<br/>Refer to the [Job Management Webservice](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/job-management/job-management-webservice.md).
`job_reference` | **String** | Reference of the Job.<br/>Refer to the [Job Management Webservice](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/job-management/job-management-webservice.md).
`job_title` | **String** | Title of the Job.<br/>Refer to the [Job Management Webservice](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/job-management/job-management-webservice.md).
`advert_id` | **Integer** | ID of the Advert.<br/>Refer to the [Advert Management Webservice](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/advert-management/advert-management-webservice.md).
`postlog_id` | **Integer** | ID of the Post.<br/>Refer to the [Advert Management Webservice](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/advert-management/advert-management-webservice.md).
`portal_id` | **Integer** | ID of the Portal to which the Post was sent.<br/>Refer to the [Portal Management Webservice](https://github.com/oneworldmarket/idibu-api/tree/master/webservices/portal-management).
`date` | **Date and time**<br/><br/>Format: `YYYY-MM-DD HH:mm:ss` | The moment of the Post reaching the Portal.

### `PostFailed`
Triggered whenever an _unsuccessful posting or deletion_ leaves the posting queue.

Please keep in mind that whether the Post is a _succcessful posting_, _successful update_, _successful deletion_, or _unsuccessful posting or deletion_ is not pre-defined and depends on the response that idibu receives from the given Portal (posting destination) after the posting or deletion attempt.

The following parameters will be passed in the body of the request:

Parameter Name | Type restrictions | Notes
-- | -- | --
`event_id` | **GUID** | ID of the event in idibu's database; please provide it when contacting support.
`type` | **String** | `PostFailed`
`client_id` | **Integer** | ID of the idibu account.
`sender_id` | **Integer** | ID of the account's User that posted the ad.<br/>Refer to the [User Management Webservice](https://github.com/oneworldmarket/idibu-api/tree/master/webservices/user-management).
`job_id` | **Integer** | ID of the Job.<br/>Refer to the [Job Management Webservice](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/job-management/job-management-webservice.md).
`job_reference` | **String** | Reference of the Job.<br/>Refer to the [Job Management Webservice](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/job-management/job-management-webservice.md).
`job_title` | **String** | Title of the Job.<br/>Refer to the [Job Management Webservice](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/job-management/job-management-webservice.md).
`advert_id` | **Integer** | ID of the Advert.<br/>Refer to the [Advert Management Webservice](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/advert-management/advert-management-webservice.md).
`postlog_id` | **Integer** | ID of the Post.<br/>Refer to the [Advert Management Webservice](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/advert-management/advert-management-webservice.md).
`portal_id` | **Integer** | ID of the Portal to which the Post was sent.<br/>Refer to the [Portal Management Webservice](https://github.com/oneworldmarket/idibu-api/tree/master/webservices/portal-management).
`date` | **Date and time**<br/><br/>Format: `YYYY-MM-DD HH:mm:ss` | The moment of the Post reaching the Portal.

### `PostUpdated`
Triggered whenever a _successful update_ leaves the posting queue.

Please keep in mind that whether the Post is a _succcessful posting_, _successful update_, or _unsuccessful posting_ is not pre-defined and depends on the response that idibu receives from the given Portal (posting destination) after the posting attempt.

The following parameters will be passed in the body of the request:

Parameter Name | Type restrictions | Notes
-- | -- | --
`event_id` | **GUID** | ID of the event in idibu's database; please provide it when contacting support.
`type` | **String** | `PostUpdated`
`client_id` | **Integer** | ID of the idibu account.
`sender_id` | **Integer** | ID of the account's User that posted the ad.<br/>Refer to the [User Management Webservice](https://github.com/oneworldmarket/idibu-api/tree/master/webservices/user-management).
`job_id` | **Integer** | ID of the Job.<br/>Refer to the [Job Management Webservice](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/job-management/job-management-webservice.md).
`job_reference` | **String** | Reference of the Job.<br/>Refer to the [Job Management Webservice](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/job-management/job-management-webservice.md).
`job_title` | **String** | Title of the Job.<br/>Refer to the [Job Management Webservice](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/job-management/job-management-webservice.md).
`advert_id` | **Integer** | ID of the Advert.<br/>Refer to the [Advert Management Webservice](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/advert-management/advert-management-webservice.md).
`postlog_id` | **Integer** | ID of the Post.<br/>Refer to the [Advert Management Webservice](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/advert-management/advert-management-webservice.md).
`portal_id` | **Integer** | ID of the Portal to which the Post was sent.<br/>Refer to the [Portal Management Webservice](https://github.com/oneworldmarket/idibu-api/tree/master/webservices/portal-management).
`date` | **Date and time**<br/><br/>Format: `YYYY-MM-DD HH:mm:ss` | The moment of the Post reaching the Portal.

---

## Webhook requests
Every webhook, when triggered, will send an HTTP POST request to the URL endpoint defined for that specific subscription.

The request's `content-type` header is always `application/x-www-form-urlencoded`, with all parameters (as defined in the section above) passed as form values.

Additionally, the `authorization` header is provided if the optional `secret` parameter has been defined for the webhook subscription (please check the [Query format](#query-format) for more details).
