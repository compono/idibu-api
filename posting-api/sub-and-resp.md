<p>A request is submitted using an HTTP POST to the address:</p>
<pre><code>http://ws.idibu.com/clients/api/REMOTE/V3/[INSERT LOGIN HASH HERE]</code></pre>
<p class="p1">The client hash is part of the the url used to post the information to, and it is mandatory that the request uses the POST method. GET request will fail with an error indicating that the payload is missing.&nbsp;</p>
<p class="p1"><strong>The xml data should be sent in a variable called:<br><br><code>xml_text</code><br><br>and must URL encoded.</strong></p>
<h1>Encoding guidelines</h1>	
<ul>
	<li>Make sure you post the data as <code>application/x-www-form-urlencoded</code> type.</lie>
	<li>Please use the UTF-8 encoding and always set the appropriate configuration tag (<code>&lt;utf8_enable&gt;yes&lt;/utf8_enable&gt;</code> sub-tag, <a href="https://github.com/oneworldmarket/idibu-api/blob/master/api-v3/vars.md" target="_blank">as per the documentation</a>).</li>
	<li>Preferably, please use HTML formatting and, even if you don't support it, please always send <code>&lt;br/&gt;</code> tags instead of plain-text newlines</li>
	<li>For any free-text fields, use CDATA.</li>
	<li>You can see an XML with special characters and their correct encoding in the <a href="https://github.com/oneworldmarket/idibu-api/tree/master/api-v3/examples">XML3 examples section</a>.</li>
</ul>
<h1 class="p1">Response Messages</h1>
<p class="p1">All messages are sent back as XML, and for succesful postings the system outputs significant logging information.</p>
<h2>Response Messages for Successful Postings</h2>
<p>For success posts you will receive a message similar to this one:</p>
<pre><code>&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot;?&gt;
&lt;IDIBU&gt;
&lt;JOB  ID=&quot;31002849&quot; STATUS=&quot;ADDED&quot;&gt;
&lt;POSTS&gt;
&lt;POST STATUS=&#39;PENDING&#39; BOARDID=&#39;54&#39; QUEUEID=&#39;846&#39; TYPE=&#39;ADD&#39; PUBLISH=&#39;2009-06-12 18:00&#39; DURATION=&#39;7&#39; /&gt;
&lt;/POSTS&gt;
&lt;/JOB&gt;
&lt;/IDIBU&gt;</code></pre>
<p class="p1">Depending on the data posted, the system may inform you of warnings/problems with the posting, even if it was successful:</p>
<pre><code>&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot;?&gt;
&lt;IDIBU&gt;
&lt;JOB  ID=&quot;31002847&quot; STATUS=&quot;ADDED&quot;&gt;
&lt;POSTS&gt;
&lt;POST STATUS=&#39;PENDING&#39; BOARDID=&#39;54&#39; QUEUEID=&#39;844&#39; TYPE=&#39;ADD&#39; PUBLISH=&#39;2009-06-12 18:00&#39; DURATION=&#39;7&#39; /&gt;
&lt;/POSTS&gt;
&lt;/JOB&gt;
&lt;LOG&gt;
&lt;WARNING FIELD=&#39;SCR_City&#39; TYPE=&#39;text&#39; BOARDID=&#39;54&#39;&gt;Field &#39;SCR_City&#39; is missing, an empty string, or contains only whitespace.&lt;/WARNING&gt;
&lt;/LOG&gt;
&lt;/IDIBU&gt;</code></pre>
<h2>Response Messages for Failed Postings</h2>
<p>In event of a posting issue you will be informed of the error. You can find below several different examples:</p>
<h3>Core Field missing</h3>
<pre><code>&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot;?&gt;
&lt;IDIBU&gt;
&lt;JOB  STATUS=&quot;FAILED&quot;&gt;
&lt;ERROR FIELD=&quot;TITLE&quot;&gt;Value was missing&lt;/ERROR&gt;
__posts__&lt;/JOB&gt;
&lt;/IDIBU&gt;</code></pre>
<h3>Incorrect Sender</h3>
<pre><code>&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot;?&gt;&lt;IDIBU&gt;
&lt;JOB  STATUS=&quot;FAILED&quot;&gt;
&lt;ERROR FIELD=&quot;SENDPROFILE&quot;&gt;6028 is not a valid sender for you.&lt;/ERROR&gt;
&lt;/JOB&gt;
&lt;/IDIBU&gt;</code></pre>
<h3>Required Extra Field missing or with incorrect value</h3>
<pre><code>&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot;?&gt;
&lt;IDIBU&gt;
&lt;JOB STATUS=&quot;FAILED&quot;&gt;&lt;ERROR&gt;There were errors in the data supplied. Please check the message log.&lt;/ERROR&gt;&lt;/JOB&gt;
&lt;LOG&gt;
&lt;ERROR FIELD=&#39;SCRlocation&#39; TYPE=&#39;doublemultiselect&#39; BOARDID=&#39;54&#39;&gt;Field &#39;SCRlocation&#39; was not supplied, or was supplied with an option that is an empty string or contains only whitespace.&lt;/ERROR&gt;
&lt;/LOG&gt;
&lt;/IDIBU&gt;</code></pre>
<h2>Response messages for delayed postings</h2>
<p>Most often the system will respond with a Post Completion Page URL - this can be passed back via the XML, or sent to the person responsible for completing the advert via email. The url links to the page where idibu asks for the remaining data to complete the posting.</p>
<pre><code>&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot; ?&gt;
&lt;idibu&gt;
&nbsp;&lt;job status=&quot;delayed&quot; id=&quot;31003254&quot; postingid=&quot;235&quot;&gt;
&nbsp;&nbsp;&lt;postcompletionurl&gt;http://adpost.idibu.com/cBzdX.html&lt;/postcompletionurl&gt;
&nbsp;&lt;/job&gt;
&nbsp;&lt;log&gt;
&nbsp;&lt;errors&gt;
&nbsp;&nbsp;&lt;error field=&#39;sco_sector&#39; type=&#39;select&#39; boardid=&#39;214&#39;&gt;Field &#39;sco_sector&#39; is missing, an empty string, or contains only whitespace.&lt;/error&gt;
&nbsp;&lt;/errors&gt;
&nbsp;&lt;warnings&gt;
&nbsp;&nbsp;&lt;warning&gt;The provided team id doesn&#39;t exists or is wrong(ID provided: 33000169)&lt;/warning&gt;
&nbsp;&nbsp;&lt;warning field=&#39;sco_location&#39; type=&#39;doubleSelect&#39; boardid=&#39;214&#39;&gt;Field &#39;sco_location&#39; was missing from the payload, but was mapped internally by the system&lt;/warning&gt;
&nbsp;&nbsp;&lt;warning field=&#39;sco_featured&#39; type=&#39;select&#39; boardid=&#39;214&#39;&gt;Field &#39;sco_featured&#39; is missing, an empty string, or contains only whitespace.&lt;/warning&gt;
&nbsp;&nbsp;&lt;warning field=&#39;idibudts_cat&#39; type=&#39;select&#39; boardid=&#39;517&#39;&gt;Field &#39;idibudts_cat&#39; was missing from the payload, but was mapped internally by the system&lt;/warning&gt;
&nbsp;&lt;/warnings&gt;
&nbsp;&lt;/log&gt;
&lt;/idibu&gt;</code></pre>
<p>We offer a great deal of configuration in this area:</p>
<ul>
	<li>We can setup a private domain with full rebranding for your users to post jobs out from</li>
	<li>The system can be configured to use any SMTP email account to provide seamless branding.</li>
	<li>The system can send out a branded confirmation email to let users know the post was successful.</li>
</ul>
Click <a href="https://github.com/oneworldmarket/idibu-api/blob/master/api-v3/quick-rep-job.md">here</a> to learn about quick reposting.
