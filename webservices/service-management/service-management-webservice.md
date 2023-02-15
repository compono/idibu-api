# Service Management Webservice
  * **[Creating an account](#creating-an-account)**
    + [Endpoint](#endpoint)
    + [Available methods](#available-methods)
    + [Query parameters](#query-parameters)
    + [Query format](#query-format)
    + [Response format](#response-format)
  * **[Listing accounts](#listing-accounts)**
    + [Endpoint](#endpoint-1)
    + [Available methods](#available-methods-1)
    + [Query parameters](#query-parameters-1)
    + [Query format](#query-format-1)
    + [Response format](#response-format-1)
  * **[Account's details](#accounts-details)**
    + [Endpoint](#endpoint-2)
    + [Available methods](#available-methods-2)
    + [Query parameters](#query-parameters-2)
    + [Query format](#query-format-2)
    + [Response format](#response-format-2)
  * **[Changing password](#changing-password)**
    + [Endpoint](#endpoint-3)
    + [Available methods](#available-methods-3)
    + [Query parameters](#query-parameters-3)
    + [Query format](#query-format-3)
    + [Response format](#response-format-3)
  * **[Listing services](#listing-services)**
    + [Endpoint](#endpoint-4)
    + [Available methods](#available-methods-4)
    + [Query parameters](#query-parameters-4)
    + [Query format](#query-format-4)
    + [Response format](#response-format-4)
  * **[Managing services](#managing-services)**
    + [Endpoint](#endpoint-5)
    + [Available methods](#available-methods-5)
    + [Query parameters](#query-parameters-5)
    + [Query format](#query-format-5)
    + [Response format](#response-format-5)

## 

This webservice allows to create a new idibu account, list and review existing accounts' data, amend their passwords, as well as list and control the available services. It also allows setting up a simple webhook for whenever a new candidate arrives on the account.

**The webservice applies to full client (admin) accounts only**. If you wish to manage users under a certain account, please use the [User Management Webservice](https://github.com/oneworldmarket/idibu-api/tree/master/webservices/user-management).

Due to the nature of this webservice, it is only available to certain partners and requires an additional `partner-password` parameter.

## Creating an account
This method allows to create a new idibu account.

### Endpoint
#### `https://ws.idibu.com/ws/rest/v1/service`

### Available methods
#### `POST /newaccount`
Creates a new account.

### Query parameters
Parameter Name | Type restrictions | Required? | Notes
-- | -- | -- | --
`idibupartner` | **String** | **Yes** | Must be set to `yes`.
`data` | **String** | **Yes** | The full query XML (see the [Query format](#query-format) below), URL-encoded within the parameter.

### Query format
```xml
<idibu>
  <partner-password>[string]</partner-password> <!-- partner password provided to you by idibu -->
  <exempt-id>[integer]</exempt-id> <!-- partner id provided to you by idibu -->
  <username>[string]</username> <!-- login username; max 32 characters -->
  <password>[string]</password> <!-- login password; max 32 characters -->
  <firstname>[string]</firstname> <!-- admin user's first name -->
  <lastname>[string]</lastname> <!-- admin user's last name -->
  <email>[string:email]</email> <!-- admin user's email address -->
  <phone>[string:phone]</phone> <!-- admin user's phone number -->
  <company-name>[string]</company-name> <!-- account's company name -->
  <user-number>[integer]</user-number> <!-- deprecated, please default to 0 -->
  <renewal-date>[string:date]</renewal-date> <!-- deprecated, please default to 20 years in the future; format: YYYY-MM-DD -->
</idibu>
```

### Response format
```xml
<idibu generator="idibu" version="1.0">
  <response>
    <message>[string]</message> <!-- 'New client successfully created' or an error message -->
    <client-hash>[string]</client-hash> <!-- hash of the created account; please keep this! -->
    <client-id>[integer]</client-id> <!-- id of the created account; please keep this! -->
    <member-id>[integer]</member-id> <!-- deprecated, please ignore -->
  </response>
  <status>["success"|"failed"]</status> <!-- whether the request succeeded or not -->
</idibu>
```

---

## Listing Accounts
This method allows viewing existing idibu accounts' details for the given Partner.

### Endpoint
#### `https://ws.idibu.com/ws/rest/v1/service`

### Available methods
#### `POST /accounts`
Returns the full list of accounts.

### Query parameters
Parameter Name | Type restrictions | Required? | Notes
-- | -- | -- | --
`idibupartner` | **String** | **Yes** | Must be set to `yes`.
`data` | **String** | **Yes** | The full query XML (see the [Query format](#query-format-1) below).
`count` | **Integer**<br/><br/>Min: 1<br/>Max: 100<br/>Default: 10 | No | Number of accounts to return.
`offset` | **Integer**<br/><br/>Min: 0<br/>Default: 0 | No | Numeric offset from where to start fetching accounts (pagination).

### Query format
```xml
<idibu>
  <partner-password>[string]</partner-password> <!-- partner password provided to you by idibu -->
  <exempt-id>[integer]</exempt-id> <!-- partner id provided to you by idibu -->
</idibu>
```

### Response format
```xml
<idibu generator="idibu" version="1.0">
  <response>
    <clients>
      <client>
        <client-hash>[string]</client-hash> <!-- hash of the account -->
        <client-id>[integer]</client-id> <!-- id of the account -->
        <username>[integer]</username> <!-- account's username -->
      </client>
    </clients>
  </response>
  <status>["success"|"failed"]</status> <!-- whether the request succeeded or not -->
</idibu>
```

---

## Account's details
This method allows obtaining more info about a particular account.

### Endpoint
#### `https://ws.idibu.com/ws/rest/v1/service`

### Available methods
#### `POST /accountdetails`
Returns the detailed info for the account with the provided `<client-id/>`.

### Query parameters
Parameter Name | Type restrictions | Required? | Notes
-- | -- | -- | --
`idibupartner` | **String** | **Yes** | Must be set to `yes`.
`data` | **String** | **Yes** | The full query XML (see the [Query format](#query-format-2) below).

### Query format
```xml
<idibu>
  <partner-password>[string]</partner-password> <!-- partner password provided to you by idibu -->
  <exempt-id>[integer]</exempt-id> <!-- partner id provided to you by idibu -->
  <client-id>[integer]</client-id> <!-- id of the account -->
</idibu>
```

### Response format
```xml
<idibu generator="idibu" version="1.0">
  <response>
    <client>
      <client-hash>[string]</client-hash> <!-- hash of the account -->
      <client-id>[integer]</client-id> <!-- id of the account -->
      <username>[integer]</username> <!-- account's username -->
      <firstname>[string]</firstname> <!-- admin user's first name -->
      <lastname>[string]</lastname> <!-- admin user's last name -->
      <email>[string:email]</email> <!-- admin user's email address -->
      <phone>[string:phone]</phone> <!-- admin user's phone number -->
      <company-name>[string]</company-name> <!-- account's company name -->
    </client>
  </response>
  <status>["success"|"failed"]</status> <!-- whether the request succeeded or not -->
</idibu>
```

---

## Changing password
This method allows to change an existing account's password.

### Endpoint
#### `https://ws.idibu.com/ws/rest/v1/service`

### Available methods
#### `POST /updateaccount`
Updates the account's password.

### Query parameters
Parameter Name | Type restrictions | Required? | Notes
-- | -- | -- | --
`idibupartner` | **String** | **Yes** | Must be set to `yes`.
`data` | **String** | **Yes** | The full query XML (see the [Query format](#query-format-3) below), URL-encoded within the parameter.

### Query format
```xml
<idibu>
  <partner-password>[string]</partner-password> <!-- partner password provided to you by idibu -->
  <exempt-id>[integer]</exempt-id> <!-- partner id provided to you by idibu -->
  <client-hash>[string]</client-hash> <!-- hash of the idibu account to which the request pertains -->
  <password>[string]</password> <!-- new login password; max 32 characters -->
</idibu>
```

### Response format
```xml
<idibu generator="idibu" version="1.0">
  <response>
    <message>[string]</message> <!-- 'Client successfully updated' or an error message -->
    <client-hash>[string]</client-hash> <!-- hash of the updated account -->
    <client-id>[integer]</client-id> <!-- id of the updated account -->
    <member-id>[integer]</member-id> <!-- deprecated, please ignore -->
  </response>
  <status>["success"|"failed"]</status> <!-- whether the request succeeded or not -->
</idibu>
```

---

## Listing services
This method allows to list services currently enabled on an account.

Available services are tied to your license agreement. **Please discuss with your idibu representative to find out which you can enable for your accounts.**

### Endpoint
#### `https://ws.idibu.com/ws/rest/v1/service`

### Available methods
#### `POST /list`
Lists all services currently enabled on an account.

### Query parameters
Parameter Name | Type restrictions | Required? | Notes
-- | -- | -- | --
`idibupartner` | **String** | **Yes** | Must be set to `yes`.
`data` | **String** | **Yes** | The full query XML (see the [Query format](#query-format-4) below), URL-encoded within the parameter.

### Query format
```xml
<idibu>
  <partner-password>[string]</partner-password> <!-- partner password provided to you by idibu -->
  <exempt-id>[integer]</exempt-id> <!-- partner id provided to you by idibu -->
  <client-hash>[string]</client-hash> <!-- hash of the idibu account to which the request pertains -->
</idibu>
```

### Response format
```xml
<idibugenerator="idibu" version="1.0">
  <response>
    <services>[string]</services> <!-- service(s) the account has enabled; multiple <service> nodes can be returned -->
  </response>
  <status>["success"|"failed"]</status> <!-- whether the request succeeded or not -->
</idibu>
```

---

## Managing services
This method allows to add or remove services from an account.

Available services are tied to your license agreement. **Please discuss with your idibu representative to find out which you should enable for your accounts.**

### Endpoint
#### `https://ws.idibu.com/ws/rest/v1/service`

### Available methods
#### `POST /add`
Adds specified services to an account.

#### `POST /remove`
Removes specified services from an account.

### Query parameters
Parameter Name | Type restrictions | Required? | Notes
-- | -- | -- | --
`idibupartner` | **String** | **Yes** | Must be set to `yes`.
`data` | **String** | **Yes** | The full query XML (see the [Query format](#query-format-5) below), URL-encoded within the parameter.

### Query format
```xml
<idibu>
  <partner-password>[string]</partner-password> <!-- partner password provided to you by idibu -->
  <exempt-id>[integer]</exempt-id> <!-- partner id provided to you by idibu -->
  <client-hash>[string]</client-hash> <!-- hash of the idibu account to which the request pertains -->
  <services>
    <service>[string]</service> <!-- service to enable or disable; multiple <service> nodes can be provided -->
  </services> 
</idibu>
```

### Response format
```xml
<idibugenerator="idibu" version="1.0">
  <response>
    <message>[string]</message> <!-- 'Services added' or 'Services removed' or an error message -->
  </response>
  <status>["success"|"failed"]</status> <!-- whether the request succeeded or not -->
</idibu>
```
