The Client Reference can be used to link the data in our system to data in the client's system, providing for easier integration.

Using a client reference makes the use of idibu job ids unnecessary, and allows for easier integration between idibu's Aptrack and the client's applicant tracking system by sending the client reference in the Aptrack applicant email metadata (please see the information that is included [here](https://github.com/compono/idibu-api/blob/master/webservices/applicant-management/applicant-management-webservice.md#applicant-email-tracking-metadata)).

Providing a client reference
============================

Using a client reference with our API is as easy as adding the corresponding tag in the requests:
```
<!-- ... -->
</config>
<job>
   <client_reference>SOM3UNIQUERef</client_reference>
   <sender id="31000383" />
   <title><![CDATA[Here goes the job title]]></title>
   <description><![CDATA[This is a job description can be long]]></description>
<!-- ... -->
```
The API will recognise and confirm the client reference by returning it in the result message:
```  
<?xml version="1.0" encoding="UTF-8" ?>
<idibu>
   <job status="added" id="31003390" client_reference="SOM3UNIQUERef">
      <posts>
         <posts status="pending" boardid="10" queueid="1802" type="add" publish="2011-07-07 00:01" duration="14" />
         <posts status="pending" boardid="41" queueid="1803" type="add" publish="2011-07-07 00:01" duration="2" />
         <posts status="pending" boardid="517" queueid="1804" type="add" publish="2011-07-07 00:01" duration="2" />
      </posts>
   </job>
</idibu>
```
Please be aware that unique client references must be used to add jobs to the system. If a client reference is sent in an ADD request, and that client reference has been used for a previous job, the system will fail the request with the following error:
```
<?xml version="1.0" encoding="UTF-8" ?>
<idibu>
   <log>
      <errors>
         <error>The Client Reference provided is already in the system, you have to provide a new reference for a new job.</error>		
      </errors>
   </log>
</idibu>
```
This is considered a critical error, so no PCP is returned.

Managing jobs using the Client Reference
========================================

The client reference can be used to manage the jobs that are already in the system instead of the idibu job id. For instance, once the job has been posted once with a client reference, updating that job is just a matter of changing the request accordingly:
```
<?xml version="1.0" encoding="UTF-8" ?>
<idibu>
 <method>UPDATE</method>
 <config>
   <show_durations>No</show_durations>
   <lockboards>YES</lockboards>
   <partnerid>yourpartnerid</partnerid>
   <redirecturl>http://www.google.com</redirecturl>
   <validate_level>Warning</validate_level>
  </config>
  <job>
   <sender id="31000383"></sender>
   <client_reference>SOM3UNIQUERef</client_reference>
   <title><![CDATA[Here goes the job title]]></title>
<!-- ... -->
```
In this case, if the system finds no quota constraints, the results are going to be exactly as above, bar the changed corresponding queue ids:
```
<?xml version="1.0" encoding="UTF-8" ?>
<idibu>
  <!-- job id matches the id informed previously by the system -->
  <job status="added" id="31003390" client_reference="SOM3UNIQUERef">
   <posts>
    <posts status="pending" boardid="10" queueid="1808" type="add" publish="2011-07-07 00:01" duration="14" />
    <posts status="pending" boardid="41" queueid="1809" type="add" publish="2011-07-07 00:01" duration="2" />
    <posts status="pending" boardid="517" queueid="1810" type="add" publish="2011-07-07 00:01" duration="2" />
   </posts>
  </job>
</idibu>
```
The same can be applied to REPOST, QUICKREPOST, DELETE, and CANCEL requests: the client reference is a complement for idibu job ids.

Updating a job's client reference
===================================

If it is needed to update or change the existing client reference of a job, then it is mandatory to use the idibu job id:
```
<!-- ... -->
</config>
   <!-- we use the job id provided by idibu -->
   <job id="31003390">
   <sender id="31000383"></sender>
   <client_reference>SOM3-New-UNIQUERef</client_reference>
   <title><![CDATA[Here goes the job title]]></title>
<!-- ... -->
```

Again, the system will acknowledge the new client reference by returning it in the result message.
