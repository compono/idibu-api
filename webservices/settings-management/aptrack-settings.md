Method gets or sets aptrack settings for an account.

## Parameters
No additional parameters for this request

## Example of getting settings
### Request
```
GET http://ws.idibu.com/ws/rest/v1/settings/aptrack?hash=<your hash>
```
### Response
```xml
<idibu generator="idibu" version="1.0">
  <response>
    <users-can-see-aptrack>no</users-can-see-aptrack>
    <statuses>
      <status>
        <extra-id>0</extra-id>
        <order>0</order>
        <name>Rejected</name>
        <label>Rejected</label>
        <enabled>yes</enabled>
        <group>general</group>
        <forward-cv>no</forward-cv>
        <has-responder>no</has-responder>
        <responder>
          <subject/>
          <body/>
        </responder>
      </status>
      <status>
        <extra-id>511</extra-id>
        <order>0</order>
        <name>Keep on file</name>
        <label>Keep on file</label>
        <enabled>no</enabled>
        <group>blue</group>
        <forward-cv>no</forward-cv>
        <has-responder>no</has-responder>
        <responder>
          <subject/>
          <body/>
        </responder>
      </status>
      <status>
        <extra-id>109</extra-id>
        <order>1</order>
        <name>Invite in for Interview</name>
        <label>Invite in for Interview</label>
        <enabled>no</enabled>
        <group>green</group>
        <forward-cv>yes</forward-cv>
        <has-responder>no</has-responder>
        <responder>
          <subject/>
          <body/>
        </responder>
      </status>
      <status>
        <extra-id>399</extra-id>
        <order>1</order>
        <name>Progress</name>
        <label>Progress</label>
        <enabled>yes</enabled>
        <group>green</group>
        <forward-cv>no</forward-cv>
        <has-responder>yes</has-responder>
        <responder>
          <subject>You have been invited for an interview</subject>
          <body><p><span>[\"Hello APPLICANT_NAME\" OR \"Dear candidate\"],<br /><br />once again, thank you for submitting your application for the position </span><span>[JOB_TITLE]. I am delighted to tell you that you have been selected to participate in the interview for this job!</span><br /> <span><br /> Please call me on&nbsp;[CONSULTANT_PHONE] to discuss further.<br /><br />Best regards,<br /><br />[CONSULTANT_NAME]<br /></span></p></body>
        </responder>
      </status>
    </statuses>
    <disable-duplicate>no</disable-duplicate>
    <auto-responders>
      <receive>
        <subject>Thank you for applying</subject>
        <body><p>{if $email.FROM_NAME eq \'No_name\' or $email.FROM_NAME eq $email.FROM_EMAIL}Dear candidate{else}Hi {$email.FROM_NAME}{/if},<br /><br />thank you for submitting your application for the position [JOB_TITLE]<em> (reference: [JOB_REFERENCE])</em>.<br /><br />Kind regards,<br /> <br /> [CONSULTANT_NAME]<br /> [CONSULTANT_EMAIL]<br />[CONSULTANT_PHONE]</p></body>
      </receive>
      <reject>
        <subject>Your application has been rejected</subject>
        <body>[\"Hi APPLICANT_NAME\" OR \"Dear candidate\"],<br /><br />unfortunately, our consultants decided that you are not suitable for this position.<br /><br />Best regards,<br /><br />[CONSULTANT_NAME]<br />[CONSULTANT_EMAIL]<br />[CONSULTANT_PHONE]</body>
      </reject>
    </auto-responders>
    <forward>
      <immediately>yes</immediately>
      <held-in-aptrack-forward-to>test@example.com</held-in-aptrack-forward-to>
      <teams/>
    </forward>
    <block-extensions>gif,jpg,jpeg,png,tif,tiff</block-extensions>
  </response>
  <status>success</status>
</idibu>
```

## Example of setting settings
- In order to change base system statuses (where `extra-id` is not set - usualy only `Rejected`), you need to provide the status name; in order to change extended (custom) statuses, you neext to provide the `extra-id`.
- Also, for base statuses, you can only change the label and disable it or enable the status. For extended statuses, by changing their label you're also changing the status name. 
- Value of `group` can be one of: `green`,`yellow`,`red`, `orange`, `blue`, `star`.
- To create a new custom status, just set `extra-id` to 0 and fill in all the appropriate fields.
- For forwarding rules, value of `immediately`; can be one of: `yes`, `no`, `teams`.

### Request
```
POST http://ws.idibu.com/ws/rest/v1/settings/system?hash=<your hash>
```
```xml
<?xml version="1.0" encoding="utf8"?>
  <idibu>
    <users-can-see-aptrack>no</users-can-see-aptrack>
    <statuses>
      <status>
        <order>0</order>
        <name>Rejected</name>
        <label>Rejected</label>
        <enabled>yes</enabled>
        <group>general</group>
        <forward-cv>no</forward-cv>
        <has-responder>no</has-responder>
        <responder>
          <subject/>
          <body/>
        </responder>
      </status>
      <status>
        <extra-id>511</extra-id>
        <order>0</order>
        <name>Keep on file</name>
        <label>Keep on file</label>
        <enabled>no</enabled>
        <group>blue</group>
        <forward-cv>no</forward-cv>
        <has-responder>no</has-responder>
        <responder>
          <subject/>
          <body/>
        </responder>
      </status>
    </statuses>
    <disable-duplicate>no</disable-duplicate>
    <forward>
      <immediately>yes</immediately>
      <held-in-aptrack-forward-to>sender</held-in-aptrack-forward-to>
      <teams/>
    </forward>
    <block-extensions>gif,jpg,jpeg,png,tif,tiff</block-extensions>
</idibu>
```
### Response
```xml
<?xml version="1.0" encoding="utf8"?>
<idibu generator="idibu" version="1.0">
  <response>
    <message>Settings updated</message>
  </response>
  <status>success</status>
</idibu>
```
