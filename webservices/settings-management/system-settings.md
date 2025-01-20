Method gets or sets system settings for an account

# Parameters
No additional parameters for this request

# Example of getting settings
## Request
```
GET https://ws.idibu.com/ws/rest/v1/settings/system?hash=<your hash>
```

## Response
```xml
<idibu generator="idibu" version="1.0">
  <response>
    <general>
      <description>There are a number of system settings that can be changed to customise your idibu system. Please be sure to contact support if you aren't completely sure of what you are doing.</description>
      <cv-search-enabled>no</cv-search-enabled>
      <delete-enabled>yes</delete-enabled>
      <force-check-spelling>no</force-check-spelling>
      <show-advert-cost>no</show-advert-cost>
      <enable-appurls>yes</enable-appurls>
      <enable-tracking>yes</enable-tracking>
    </general>
    <user-access>
      <description>Change settings to provide non-admin users different levels of access to the system.</description>
      <filter-profile-jobs>no</filter-profile-jobs>
      <disable-default-post-profile>no</disable-default-post-profile>
      <strip-phone-numbers>yes</strip-phone-numbers>
      <disable-normal-repost>no</disable-normal-repost>
      <disable-quick-repost>no</disable-quick-repost>
      <disable-job-template>no</disable-job-template>
    </user-access>
    <alerts>
      <description>idibu provides important alerts by email - for posting errors and for when adverts are expiring on the job boards. You can set these alerts to be sent the sender of the advert, the administrator of this account, or both.</description>
      <auto-error-mode>Admin</auto-error-mode>
      <auto-expiry-emails>Sender</auto-expiry-emails>
    </alerts>
    <country>
      <description>Set the default country to be used by locations in the system.</description>
      <location-country>GB</location-country>
    </country>
    <footer>
      <description>Add text to be appended to all job descriptions sent out by idibu (Please refrain from entering e-mail addresses, phone numbers or URLs, as this can increase likelihood of boards rejecting your adverts).</description>
      <jobDisclaimer>
        <ul>
          <li>
            <strong>plain text footer</strong>
          </li>
          <li>
            <em>plain footer</em>
          </li>
          <li>footer</li>
        </ul> Idibu &pound; $ &amp; % @ ! ? . , = &euro; Ą ą Ć &Uuml; &uuml; &szlig; x y z</jobDisclaimer>
    </footer>
  </response>
  <status>success</status>
</idibu>
```
# Example of setting settings
## Request
```
POST https://ws.idibu.com/ws/rest/v1/settings/system?hash=<your hash>
```
```xml
<?xml version="1.0"?>
<idibu>
  <cv-search-enabled>yes</cv-search-enabled>
  <email-template-auth>
    <subject>subject of auth message</subject>
    <body>Body of auth message</body>
  </email-template-auth>
</idibu>
```
# idibu interface reference
![image](https://user-images.githubusercontent.com/2776439/167879899-c65f063b-2cc1-445d-b0a6-eb6342ee7fcb.png)
