## Listing credits
This method allows listing all client accounts and their number of Pay Per Post credits. It also provides the total Pay Per Post credits belonging to your Partner account, as well as the number currently assigned to client accounts and the number still available to assign.

Pay Per Post credits are only available for certain Partners and will be enabled if your agreement includes them.

### Endpoint
#### `https://ws.idibu.com/ws/rest/v1/service`

### Available methods
#### `GET /viewCredits`
Lists the total number of credits, the number of assigned and available credits, as well as all client accounts and the number of credits assigned to them.

### Query parameters
Parameter Name | Type restrictions | Required? | Notes
-- | -- | -- | --
`data` | **String** | **Yes** | The full query XML (see the [Query format](#query-format-4) below), URL-encoded within the parameter.
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
This method allows to add or remove credits from an account - either by assigning a specific value or by incrementing/decrementing by a certain number.

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
`data` | **String** | **Yes** | The full query XML (see the [Query format](#query-format-5) below), URL-encoded within the parameter.

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
