<p>When you post advert using Adpost service - it returns response like this:</p>
<p>&nbsp;</p>
<pre wrap="">
<code type="xml">
&lt;job id=&quot;37014682&quot; status=&quot;added&quot;&gt;
		&lt;posts&gt;
			&lt;posts boardid=&quot;10&quot; duration=&quot;7&quot; publish=&quot;2013-06-17 00:00&quot; queueid=&quot;8734509&quot; status=&quot;pending&quot; type=&quot;add&quot;&gt;
			&lt;posts boardid=&quot;1462&quot; duration=&quot;28&quot; publish=&quot;2013-06-17 00:00&quot; queueid=&quot;8734510&quot; status=&quot;pending&quot; type=&quot;add&quot;&gt;
		&lt;/posts&gt;
	&lt;/posts&gt;&lt;/posts&gt;&lt;/job&gt;
</code>
</pre>
<p>This service can be use to check status of added postings. You have to get <em>queueid</em> from returned response and put it into pq-id variable of the adverts/posting method.</p>
<h1>
	Example</h1>
<h2>
	Request</h2>
<p>GET&nbsp;&nbsp; /ws/rest/v1/adverts/posting?<strong>pq-id=8734509</strong>&amp;hash=&lt;put your hash here&gt;</p>
<h2>Example Error Response</h2>
<pre wrap="">
<code type="xml">
&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
&lt;response&gt;
	&lt;portal&gt;
		&lt;id&gt;10&lt;/id&gt;
		&lt;url&gt;www.reed.co.uk&lt;/url&gt;
		&lt;logo&gt;reed3.jpg&lt;/logo&gt;
		&lt;name&gt;Reed&lt;/name&gt;
	&lt;/portal&gt;
	&lt;post&gt;
		&lt;start&gt;2013-06-17 10:44:06&lt;/start&gt;
		&lt;stop&gt;2013-06-24 00:00:00&lt;/stop&gt;
		&lt;type&gt;post&lt;/type&gt;
		&lt;status&gt;fail&lt;/status&gt;
		&lt;deletable&gt;no&lt;/deletable&gt;
		&lt;errordetails&gt;
			&lt;errordetail&gt;
				&lt;description&gt;The job board server sent us a message to say that the username or password connected to the ad are incorrect.&lt;/description&gt;
				&lt;solution&gt;1. Contact Reed to check the config details entered in idibu.&lt;br /&gt;
					2. Once confirmed: &lt;br /&gt;
					a) login to  &lt;a href=&quot;?class=Client&amp;action=PortalConfig&quot;&gt;here&lt;/a&gt;&lt;br /&gt;
					b) click &amp;quot;Job boards and quotas&amp;quot; &lt;br /&gt;
					c) click &amp;quot;Settings&amp;quot; next to the Reed and amend the details&lt;br /&gt;
					d) click &amp;quot;Save settings&amp;quot;&lt;/solution&gt;
			&lt;/errordetail&gt;
		&lt;/errordetails&gt;
	&lt;/post&gt;
	&lt;expired&gt;no&lt;/expired&gt;
	&lt;applicants&gt;&lt;/applicants&gt;
	&lt;link /&gt;
&lt;/response&gt;
&lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>

<h2>Example Success Response</h2>
<pre wrap="">
<code type="xml">
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
&lt;response&gt;
	&lt;portal&gt;
		&lt;id&gt;338&lt;/id&gt;
		&lt;url&gt;www.seek.com.au&lt;/url&gt;
		&lt;logo&gt;seek2014.png&lt;/logo&gt;
		&lt;name&gt;Seek&lt;/name&gt;
		&lt;/portal&gt;
	&lt;post&gt;
		&lt;start&gt;2017-06-25 00:57:02&lt;/start&gt;
		&lt;stop&gt;2017-07-01 03:42:00&lt;/stop&gt;
		&lt;type&gt;update&lt;/type&gt;
		&lt;status&gt;success&lt;/status&gt;
		&lt;deletable&gt;no&lt;/deletable&gt;
	&lt;/post&gt;
&lt;expired&gt;yes&lt;/expired&gt;
&lt;applicants/&gt;
&lt;link&gt;
https://adposting.cloud.seek.com.au/advertisement/817d3231-2ab0-45d7-a623-a7ff2c023114/view
&lt;/link&gt;
&lt;/response&gt;
&lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
