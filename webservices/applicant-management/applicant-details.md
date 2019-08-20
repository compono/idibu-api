<p>Method returns applicant details. If client has CV parsing enabled on his account, the parsed data will be included in the &quot;parsed&quot; tag. Mind that there is an extra charge for the client if the parsed data would be used in an external system.<br />
	<br />
	<code>GET: ws.idibu.com/ws/rest/v1/applicants/1234?hash=YOUR_HASH</code>
</p>
<h2>Response</h2>

```xml

<idibu generator="idibu" version="1.0">
    <response><id>39078652</id>
        <email>f_emore@yahoo.co.uk</email>
        <name>Fola Emore</name>
        <job>
            <id>37003486</id>
            <reference>J712</reference>
        </job>
        <date>2013-02-19 15:08:13</date>
        <message>
            <subject>CityJobs Application 219930-J712 (People Change Project Manager) (South West London)</subject>
            <message>
                <text>
                    Please find an application for the following CityJobs vacancy :-
                    219930-J712 (People Change Project Manager) (South West London)
                    COVERING LETTER
                    Having seen details of vacancy 219930-J712 (People Change Project Manager) advertised by CityJobs, I would like to apply for the position.
                    Please find a copy of my CV attached.
                </text>
            </message>
            <portal>
                <id>57</id>
                <name>City Jobs</name>
            </portal>
            <status>Rejected</status>
            <files>
                <file>
                    <name>121784969.doc</name>
                    <link>http://ws.idibu.com/down.php?id=1001481&amp;file=28B63807593EABD603343432A1C6922D.doc</link>
                </file>
            </files>
        </message></response>
    <status>success</status>
</idibu>

```
