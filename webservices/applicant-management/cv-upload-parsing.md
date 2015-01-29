You can upload applicant data into idibu.

This is useful if you want legacy applicant data to be available via our local search, or you have arranged to have fully parsed data handed back to you.

<p>Method imports CV into the idibu&nbsp;local search database.</p>
<p>Use the job id and reference to define which job the applicant will be attached to, these are required fields.</p>
<p>Don&#39;t worry if you can&#39;t supply email or first/last names, we&#39;ll try to grab those from the CV itself.</p>
<p>Please note that CV contents should be base64 encoded, file name shouldn&#39;t contain any extra symbols. <br />
You can also specify application`s source, subject and body of what would normally be applicant's incoming email.</p>
<div>
<h1 class="p3">Link:</h1>
http://ws.idibu.com/ws/rest/v1/applicants/add-cv?hash=(account`s hash)

	<h1 class="p3">
		Example</h1>
	<h2>
		Request</h2>
	<pre>
<code type="xml">
&lt;idibu&gt;
    &lt;job&gt;
        &lt;id&gt;(direct or base64 encoded idibu job id)&lt;/id&gt;
        &lt;!-- &lt;reference&gt;ABC123&lt;/reference&gt; -- job reference is no longer required (it is always fetched from db) --&gt;
        &lt;portal&gt;aeo&lt;/portal&gt; &lt;!-- portal BID or id can be provided --&gt;
        &lt;!-- if there is a portal id, latest postlog id will be fetched from db --&gt;
    &lt;/job&gt;
    &lt;cv&gt;
        &lt;name&gt;cv.doc&lt;/name&gt;
        &lt;contents&gt;BASE64+ENCODED+FILE+CONTENT&lt;/contents&gt;
    &lt;/cv&gt;
    &lt;email&gt;
        &lt;from&gt;darek@idibu.com&lt;/from&gt; &lt;!-- ability to specify email from address --&gt;
        &lt;subject&gt;Application from me&lt;/subject&gt; &lt;!-- ability to specify email subject --&gt;
        &lt;body&gt;Accept me, pretty please&lt;/body&gt; &lt;!-- ability to specify email body --&gt;
    &lt;/email&gt;
&lt;/idibu&gt;
</code></pre>
</div>
<p>&nbsp;</p>
