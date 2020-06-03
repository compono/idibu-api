You can upload applicant data into idibu.

This is useful if you want legacy applicant data to be available via our local search, or you have arranged to have fully parsed data handed back to you.

<p>Method imports CV into the idibu&nbsp;local search database.</p>
<p>Use the job id and reference to define which job the applicant will be attached to, these are required fields.</p>
<p>Don&#39;t worry if you can&#39;t supply email or first/last names, we&#39;ll try to grab those from the CV itself.</p>
<p>Please note that CV contents should be base64 encoded, file name shouldn&#39;t contain any extra symbols. <br />
You can also specify application's source, subject and body of what would normally be applicant's incoming email.<br />
Please note that this will upload the CV and trigger applicant forwarding as email as if this CV arrived directly from Job board.</p>
<div>
<h1 class="p3">Link:</h1>
http://ws.idibu.com/ws/rest/v1/applicants/add-cv?hash=(account's_hash)

<h1 class="p3">Example Request</h1>
<pre>
&lt;idibu&gt;
    &lt;job&gt;
        &lt;id&gt;(direct or base64 encoded idibu job id)&lt;/id&gt; &lt;!-- required --&gt;
        &lt;portal&gt;aeo&lt;/portal&gt; &lt;!-- portal BID or id can be provided --&gt;
        &lt;!-- if job and portal id is present, latest post to that portal will be used --&gt;
        &lt;!-- if no portal id is provided, idibu CV manager (id: 1229) will be used --&gt;
        &lt;!-- if there are no previous postings to idibu CV manager, a new post will be created and the applicant uploaded against it --&gt;
    &lt;/job&gt;
    &lt;cv&gt;
        &lt;name&gt;cv.doc&lt;/name&gt;
        &lt;contents&gt;BASE64+ENCODED+FILE+CONTENT&lt;/contents&gt;
    &lt;/cv&gt;
    &lt;email&gt;
        &lt;from&gt;email@example.com&lt;/from&gt; &lt;!-- ability to specify email from address --&gt;
        &lt;subject&gt;Application from me&lt;/subject&gt; &lt;!-- ability to specify email subject --&gt;
        &lt;body&gt;Accept me, pretty please&lt;/body&gt; &lt;!-- ability to specify email body --&gt;
    &lt;/email&gt;
&lt;/idibu&gt;
</pre>

Portal BIDs (used for the <code>&lt;portal&gt;</code> field) can be found here:

http://www.idibu.com/clients/?user=<b>[Your idibu username]</b>&password=<b>[Your idibu password]</b>&class=Portal&action=ListBIDs

or you can use <a href="https://github.com/oneworldmarket/idibu-api/blob/master/webservices/portal-management/portal-details/get-portal-details.md" target="_blank">this webservice</a> to obtain the ids.

Below is a code snippet that can be used to quickly utilize this ws:

https://github.com/oneworldmarket/idibu-api/blob/master/webservices/code-library/CV_upload_php.md

</div>
<p>&nbsp;</p>
