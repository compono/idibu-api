This API provides another method of identifying jobs in idibu besides the returned job id.

When a job is created in idibu, the system returns the unique job id in the response message - this can then be used by the remote system to link the job posted to the data in idibu. 

Our API also accepts a tag called <client_reference>. This tag should contain an alphanumeric string, that will uniquely identify this particular job inside idibu, and can be used to update, repost, etc. the job - and it will be sent in the applicant tracking emails to allow you to create reporting statistics.

The remote system is in charge of generating these references, and sending that info with the payload. Ideally the first time a reference is sent it will be sent by making an ADD request, and all subsequent requests will be either UPDATE or REPOST. Trying to ADD a job with a reference that exists previously in the system will fail and return with an error message, and the same thing will happen when trying to UPDATE or REPOST a job by sending a client reference that hasn't been used before.

It is possible to use the API referencing jobs only with the client reference in the way stated above; it is possible as well to use the API referencing jobs only with the ids provided by idibu, and a mixture of both is possible as well.

It's the entirely responsibility of the posting party to manage and administer the client references used.

<a href="https://github.com/oneworldmarket/idibu-api/blob/master/api-v3/pcp.md">Click here to continue reading about Post Completion Page - the PCP.</a>
