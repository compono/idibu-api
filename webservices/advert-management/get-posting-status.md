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
<h2>
	Response</h2>
<pre wrap="">
<code type="xml">
<?xml version="1.0" encoding="utf-8"?>
<idibu generator="idibu" version="1.0"><response><portal><id>10</id><url>www.reed.co.uk</url><logo>reed3.jpg</logo><name>Reed</name></portal><post><start>2013-06-17 10:44:06</start><stop>2013-06-24 00:00:00</stop><type>post</type><status>fail</status><deletable>no</deletable><errordetails><errordetail><description>The job board server sent us a message to say that the username or password connected to the ad are incorrect.</description><solution>1. Contact Reed to check the config details entered in idibu.&lt;br /&gt;
2. Once confirmed: &lt;br /&gt;
&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;a) login to  &lt;a href=&quot;?class=Client&amp;action=PortalConfig&quot;&gt;here&lt;/a&gt;&lt;br /&gt;
&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;b) click &amp;quot;Job boards and quotas&amp;quot; &lt;br /&gt;
&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;c) click &amp;quot;Settings&amp;quot; next to the Reed and amend the details&lt;br /&gt;
&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;d) click &amp;quot;Save settings&amp;quot;</solution></errordetail></errordetails></post><expired>no</expired><applicants></applicants><link /></response><status>success</status></idibu>
</code></pre>
