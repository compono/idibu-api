Upon processing a candidate the external system should send an HTTP POST request to the following endpoint:
http://ws.idibu.com/ws/rest/v1/applicant-status/:applicant-id?hash=:hash
The request should contain an XML payload encapsulated in a x-www-form-urlencoded request, in a field called data, like so:
POST /ws/rest/v1/applicant-status/123?hash=456
Host: ws.idibu.com
Content-Type: application/x-www-form-urlencoded


data=%3Cxml%3Epayload%3C%2Fxml%3E…
The XML payload should follow the specified format:
<applicant>
	<status>:status</status>
	<remote-id>:remote-id</remote-id>
	<error-message>:error-message</error-message>
	<date-processed>:date-processed</date-processed>
</applicant>
If the status is successfully stored, the endpoint will return a success status message (may also contain other information):
<idibu>
<status>success</status>
</idibu>
The fields used in the request are:
:hash	Client API hash
:applicant-id	Applicant ID (X-iTrackID header in the AppTrack forwarded email)
:status	String describing the status of candidate processing, expected either success or fail
:remote-id	(optional) Any string to identify the applicant in remote system
:error-message	(optional) Error message detailing the problem that occurred while processing the application, expected on fail status
:date-processed	(optional) Date and time at which the application was processed, if empty current date is used, expected in YYYY-MM-DD hh:mm:ss format
Example of a correct request for a successfully processed application:
<applicant>
	<status>success</status>
	<date-processed>2016-06-03 12:11:59</date-processed>
</applicant>
Example of a correct request for an unsuccessfully processed application:
<applicant>
	<status>fail</status>
	<error-message>Candidate application has been eaten by a stray dog</error-message>
	<date-processed>2016-06-03 13:07:34</date-processed>
</applicant>
Sending multiple requests for the same applicant will result in updating the information in idibu.
It is also possible to then remotely check the status of the candidate based on idibu’s candiate ID or based on the remote ID provided:
Option 1
GET /ws/rest/v1/applicant-status/:id?hash=:hash


Returns data for a particular AppTrack id :id.

Option 2
GET /ws/rest/v1/applicant-status?hash=:hash


Returns all client applicants' statuses (as in all WSes limited to 10 by default, can be browsed with offset and limit params).
Option 3
GET /ws/rest/v1/applicant-status?hash=:hash&remote-id=:remote-id


Returns applicants' statuses matching the :remote-id provided. Wildcard * can be used.
