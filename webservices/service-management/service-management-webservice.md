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
  * **[Updating an account](#updating-an-account)**
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
  * **[Listing credits](#listing-credits)**
    + [Endpoint](#endpoint-6)
    + [Available methods](#available-methods-6)
    + [Query parameters](#query-parameters-6)
    + [Query format](#query-format-6)
    + [Response format](#response-format-6)
  * **[Managing credits](#managing-credits)**
    + [Endpoint](#endpoint-7)
    + [Available methods](#available-methods-7)
    + [Query parameters](#query-parameters-7)
    + [Query format](#query-format-7)
    + [Response format](#response-format-7)

## 

This webservice allows creating a new idibu account, list and review existing accounts' data, amend their passwords, as well as list and control the available services. It also allows setting up a simple webhook for whenever a new candidate arrives on the account.

**The webservice applies to full client (admin) accounts only**. If you wish to manage users under a certain account, please use the [User Management Webservice](https://github.com/oneworldmarket/idibu-api/tree/master/webservices/user-management).

Due to the nature of this webservice, it is only available to certain partners and requires an additional `partner-password` parameter.

## Creating an account
This method allows creating a new idibu account.

### Endpoint
#### `https://ws.idibu.com/ws/rest/v1/service`

### Available methods
#### `POST /newaccount`
Creates a new account.

### Query parameters
Parameter Name | Type restrictions | Required? | Notes
-- | -- | -- | --
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
  <company-name>[string]</company-name> <!-- account's company name -->
  <address>[string]</address> <!-- account's company address; optional -->
  <address1>[string]</address1> <!-- address line 1 -->
  <address2>[string]</address2> <!-- address line 2; optional -->
  <address3>[string]</address3> <!-- address line 3 (County or State); optional -->
  <country>[string]</country> <!-- the main country in which the company resides -->
  <postcode>[string]</postcode> <!-- account's company postal code -->
  <phone>[string:phone]</phone> <!-- account's primary phone number -->
  <fax>[string:phone]</fax> <!-- account's primary fax; optional -->
  <www>[string:url]</www> <!-- the address of the company's website -->
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
      <address>[string]</address> <!-- account's company address -->
      <address1>[string]</address1> <!-- address line 1 -->
      <address2>[string]</address2> <!-- address line 2 -->
      <address3>[string]</address3> <!-- address line 3 (County or State) -->
      <country>[string]</country> <!-- the main country in which the company resides -->
      <postcode>[string]</postcode> <!-- account's company postal code -->
      <fax>[string:phone]</fax> <!-- account's primary fax -->
      <www>[string:url]</www> <!-- the address of the company's website -->
    </client>
  </response>
  <status>["success"|"failed"]</status> <!-- whether the request succeeded or not -->
</idibu>
```

---

## Updating an account
This method allows changing some of the account's details.

### Endpoint
#### `https://ws.idibu.com/ws/rest/v1/service`

### Available methods
#### `POST /updateaccount`
Updates the account's password.

### Query parameters
Parameter Name | Type restrictions | Required? | Notes
-- | -- | -- | --
`data` | **String** | **Yes** | The full query XML (see the [Query format](#query-format-3) below), URL-encoded within the parameter.<br/>Only fields that need updating can be provided.

### Query format
```xml
<idibu>
  <partner-password>[string]</partner-password> <!-- partner password provided to you by idibu -->
  <exempt-id>[integer]</exempt-id> <!-- partner id provided to you by idibu -->
  <client-hash>[string]</client-hash> <!-- hash of the idibu account to which the request pertains -->
  <password>[string]</password> <!-- new login password; max 32 characters -->
  <firstname>[string]</firstname> <!-- new admin user's first name -->
  <lastname>[string]</lastname> <!-- new admin user's last name -->
  <email>[string:email]</email> <!-- new admin user's email address -->
  <company-name>[string]</company-name> <!-- new account's company name -->
  <address>[string]</address> <!-- new account's company address -->
  <address1>[string]</address1> <!-- new address line 1 -->
  <address2>[string]</address2> <!-- new address line 2 -->
  <address3>[string]</address3> <!-- new address line 3 (County or State) -->
  <country>[string]</country> <!-- new the main country in which the company resides -->
  <postcode>[string]</postcode> <!-- new account's company postal code -->
  <phone>[string:phone]</phone> <!-- new account's primary phone number -->
  <fax>[string:phone]</fax> <!-- new account's primary fax -->
  <www>[string:url]</www> <!-- new the address of the company's website -->
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
This method allows listing services currently enabled on an account.

Available services are tied to your license agreement. **Please discuss with your idibu representative to find out which you can enable for your accounts.**

### Endpoint
#### `https://ws.idibu.com/ws/rest/v1/service`

### Available methods
#### `POST /list`
Lists all services currently enabled on an account.

### Query parameters
Parameter Name | Type restrictions | Required? | Notes
-- | -- | -- | --
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
This method allows adding or removing services from an account.

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

---

## Listing credits
This method allows listing all client accounts for the given Partner and their number of Pay Per Post credits. It also provides the total Pay Per Post credits belonging to the Partner account, as well as the number currently assigned to client accounts and the number still available to assign.

Pay Per Post credits are only available for certain Partners and will be enabled if your license agreement includes them.

### Endpoint
#### `https://ws.idibu.com/ws/rest/v1/service`

### Available methods
#### `GET /viewCredits`
Lists the total number of credits, the number of assigned and available credits, as well as all client accounts and the number of credits assigned to them.

### Query parameters
Parameter Name | Type restrictions | Required? | Notes
-- | -- | -- | --
`data` | **String** | **Yes** | The full query XML (see the [Query format](#query-format-6) below), URL-encoded within the parameter.
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
<idibugenerator="idibu" version="1.0">
  <response>
    <creditsInfo>
      <available>[integer]</available> <!-- number of credits that can be distributed among clients -->
      <allocated>[integer]</allocated> <!-- number of credits currently assigned to clients -->
      <total>[integer]</total> <!-- total number of credits -->
    </creditsInfo>
    <clients>
      <client>
        <client-hash>[string]</client-hash> <!-- hash of the account -->
        <client-id>[integer]</client-id> <!-- id of the account -->
        <username>[integer]</username> <!-- account's username -->
        <credits>[integer]</credits> <!-- number of credits assigned to the account -->
      </client>
    </clients>
  </response>
  <status>["success"|"failed"]</status> <!-- whether the request succeeded or not -->
</idibu>
```

---

## Managing credits
This method allows adding or removing Pay Per Post credits from an account - either by assigning a specific value or by incrementing/decrementing by a certain number.

Pay Per Post credits are only available for certain Partners and will be enabled if your license agreement includes them.

### Endpoint
#### `https://ws.idibu.com/ws/rest/v1/service`

### Available methods
#### `POST /setCredits`
Assignes a specified number of credits to the account.

#### `POST /incrementCredits`
Increases (or decreases if negative) the account's credits by a specified number.

### Query parameters
Parameter Name | Type restrictions | Required? | Notes
-- | -- | -- | --
`data` | **String** | **Yes** | The full query XML (see the [Query format](#query-format-7) below), URL-encoded within the parameter.

### Query format
```xml
<idibu>
  <partner-password>[string]</partner-password> <!-- partner password provided to you by idibu -->
  <exempt-id>[integer]</exempt-id> <!-- partner id provided to you by idibu -->
  <client-hash>[string]</client-hash> <!-- hash of the idibu account to which the request pertains -->
  <credits>[integer]</credits> <!-- number of credits to assign or to add/remove -->
</idibu>
```

### Response format
```xml
<idibugenerator="idibu" version="1.0">
  <response>
    <message>[string]</message> <!-- 'Credits updated successfully' or 'Credits incremented successfully' or an error message -->
    <client-id>[string]</client-id> <!-- id of the account -->
    <credits>[integer]</credits> <!-- current number of credits assigned to the account, following the change -->
  </response>
  <status>["success"|"failed"]</status> <!-- whether the request succeeded or not -->
</idibu>
```
