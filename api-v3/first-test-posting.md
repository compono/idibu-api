<p>You can use the XML below to provide a proof of concept post. To do this you&#39;ll need to:</p>
<ul>
	<li>
		Add these boards to your idibu account: a) idibu Developer Board (id 517), b) Supply Chain Online (id 214), c) Jobsite (id 41) and d) CV-Library (id 39) - just add test/test login credentials for the boards, if you do post a adverts they will fail to be accepted by the boards, though posts should work to our developer board.</li>
	<li>
		You will find an XML test page at <a href="http://www.idibu.com/get_xml_jobs.php" target="_blank">http://www.idibu.com/get_xml_jobs.php</a> - ensure it is in &#39;V3&#39; mode, add your HASH code and the XML to post into the system</li>
	<li>
		You will need to find the Team ID of your sender profile, check for the ID inside idibu when you hover over the Team to edit it</li>
	<li>
		The XML below posts to four boards - we have added extra fields for Supply Chain Online so you can see how you can optionally send this data through, or alternatively just let your advert posters complete these details on the posting completion page</li>
	<li>
		The redirect URL takes you to Google, this can of course be changed to whatever you want</li>
</ul>
<pre>
<code>
&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot;?&gt;
&lt;idibu&gt;
&lt;method&gt;add&lt;/method&gt;
&lt;config&gt;
&lt;show_durations&gt;no&lt;/show_durations&gt;
&lt;completionurl&gt;email&lt;/completionurl&gt;
&lt;advertcompletionemail&gt;bob@bob.com&lt;/advertcompletionemail&gt;
&lt;lockboards&gt;yes&lt;/lockboards&gt;
&lt;redirecturl&gt;http://www.google.com &lt;/redirecturl&gt;
&lt;validate_level&gt;warning&lt;/validate_level&gt;
&lt;/config&gt;
&lt;job&gt;
&lt;title&gt;&lt;![CDATA[Account Manager - Technical Sourcing]]&gt;&lt;/title&gt;
&lt;reference&gt;ABC123456789&lt;/reference&gt;
&lt;description&gt;&lt;![CDATA[Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus quis metus in felis tincidunt ullamcorper quis at ante. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nam ultrices mattis tortor, eget cursus tellus placerat at.]]&gt;&lt;/description&gt;
&lt;sender&gt;
&lt;team id=&quot;33000169&quot; /&gt;
&lt;name&gt;Steve&lt;/name&gt;
&lt;lastname&gt;Rogers&lt;/lastname&gt;
&lt;email&gt;test@mail.net&lt;/email&gt;
&lt;company&gt;One World Market&lt;/company&gt;
&lt;phone&gt;+44 (0) 111-1111111&lt;/phone&gt;
&lt;www&gt;http://uk.idibu.com &lt;/www&gt;
&lt;country&gt;UK&lt;/country&gt;
&lt;postcode&gt;020 1111 1111&lt;/postcode&gt;
&lt;/sender&gt;
&lt;category id=&quot;21&quot; /&gt;
&lt;location id=&quot;8&quot; /&gt;
&lt;sublocation id=&quot;668&quot; /&gt;
&lt;jobtype id=&quot;2&quot; /&gt;
&lt;startdate&gt;2010-11-26&lt;/startdate&gt;
&lt;duration&gt;Full time&lt;/duration&gt;
&lt;salarymin&gt;20000&lt;/salarymin&gt;
&lt;salarymax&gt;25000&lt;/salarymax&gt;
&lt;salaryper value=&quot;annum&quot; /&gt;
&lt;currency&gt;GBP&lt;/currency&gt;
&lt;publish&gt;2010-11-26&lt;/publish&gt;
&lt;posts&gt;
&lt;board id=&quot;214&quot;&gt;
&lt;duration days=&quot;21&quot; /&gt;
&lt;extrafield name=&quot;sco_sector&quot;&gt;&lt;item id=&quot;15&quot; /&gt;&lt;/extrafield&gt;
&lt;extrafield name=&quot;sco_featured&quot;&gt;&lt;item id=&quot;no&quot; /&gt;&lt;/extrafield&gt;
&lt;extrafield name=&quot;sco_location&quot; parent=&quot;82&quot;&gt;&lt;!-- double select --&gt;
&lt;item id=&quot;85&quot; /&gt;
&lt;/extrafield&gt;
&lt;extrafield name=&quot;sco_summary&quot;&gt;testing text for text area&lt;!-- text area --&gt;
&lt;/extrafield&gt;
&lt;extrafield name=&quot;sco_locover&quot;&gt;London&lt;/extrafield&gt;
&lt;extrafield name=&quot;cso_osal&quot;&gt;No benefits&lt;/extrafield&gt;
&lt;/board&gt;
&lt;board id=&quot;517&quot;&gt;
&lt;duration days=&quot;7&quot; /&gt;
&lt;/board&gt;
&lt;board id=&quot;41&quot;&gt;
&lt;duration days=&quot;1&quot; /&gt;
&lt;/board&gt;
&lt;board id=&quot;39&quot;&gt;
&lt;duration days=&quot;7&quot; /&gt;
&lt;/board&gt;
&lt;/posts&gt;
&lt;/job&gt;
&lt;/idibu&gt;
</code></pre>
<h1>
	Common issues</h1>
<p>Q: I&#39;m getting errors like &quot;The DESCRIPTION tag is missing from the xml payload&quot;</p>
<p>A: Make sure you URL encode the XML payload rather than passing it as XML.</p>
<p>Q: I get a response the board &#39;x&#39; is not in our current subscribed list?</p>
<p>A: Make sure you have an active subscription to the board you are posting to. In your idibu account, go to job board subscriptions, inactive tab - and subscribe to the board you want to post to.</p>
<p>Q: Do I need to send the board login details in with the XML?</p>
<p>A: When you add a job board inside idibu you give the admin details there - when you post a job the system uses these fields to post the job to the board. You can optionally send these extra fields in the XML instead. If you do so they will override the board login details already loaded inside your account for that board.</p>

Be sure to check our <a href="https://github.com/oneworldmarket/idibu-api/tree/master/api-v3/examples">XML examples to help you developing</a>.

Before you begin coding, perphas worth to check <a href="https://github.com/oneworldmarket/idibu-api/blob/master/webservices/code-library/.net-basic-interaction.md" target="_blank">our code library</a> in case there's something you can re-use and save time?

Good luck and happy postin!
