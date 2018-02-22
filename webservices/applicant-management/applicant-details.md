<p>Method returns applicant details. If client has CV parsing enabled on his account, the parsed data will be included in the &quot;parsed&quot; tag. Mind that there is an extra charge for the client if the parsed data would be used in an external system.<br />
	<br />
	<code>GET: ws.idibu.com/ws/rest/v1/applicants/1234?hash=YOUR_HASH</code>
</p>
<h2>Response</h2>
<pre><code type="xml">&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
&lt;response&gt;&lt;id&gt;39078652&lt;/id&gt;
&lt;email&gt;f_emore@yahoo.co.uk&lt;/email&gt;
&lt;name&gt;Fola Emore&lt;/name&gt;
&lt;job&gt;
	&lt;id&gt;37003486&lt;/id&gt;
	&lt;reference&gt;J712&lt;/reference&gt;
&lt;/job&gt;
&lt;date&gt;2013-02-19 15:08:13&lt;/date&gt;
&lt;message&gt;
&lt;subject&gt;CityJobs Application 219930-J712 (People Change Project Manager) (South West London)&lt;/subject&gt;
&lt;message&gt;
	&lt;text&gt;
	Please find an application for the following CityJobs vacancy :-
	219930-J712 (People Change Project Manager) (South West London)
	COVERING LETTER
	Having seen details of vacancy 219930-J712 (People Change Project Manager) advertised by CityJobs, I would like to apply for the position.
	Please find a copy of my CV attached.
	&lt;/text&gt;
&lt;/message&gt;
&lt;portal&gt;
&lt;id&gt;57&lt;/id&gt;
&lt;name&gt;City Jobs&lt;/name&gt;
&lt;/portal&gt;
&lt;status&gt;Rejected&lt;/status&gt;
&lt;files&gt;
	&lt;file&gt;
		&lt;name&gt;121784969.doc&lt;/name&gt;&lt;link /&gt;http://ws.idibu.com/down.php?id=1001481&amp;amp;file=28B63807593EABD603343432A1C6922D.doc
		&lt;/file&gt;
	&lt;/files&gt;
&lt;/message&gt;&lt;/response&gt;
&lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
