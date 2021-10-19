_**This document is outdated. Please refer to the new version [HERE](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/applicant-management/applicant-management-webservice.md).**_

<details>
 <summary><i>Show me anyway</i></summary>
    
<p>Method allows to delete all instances of a particular applicant (or set of applicants) either by their ID or e-mail address.</p>
<p>Candidate records are queued for deletion which, in case of large amount of requests, may not be processed immediately. Due to this, the method also doesn't check for the amount or validity of the requested records, and will therefore always return successful response, even if there is nothing to remove.</p>
<p><strong>Please note that once you action the removal of the candidate's data, this process cannot be reversed in any circumstances.</strong> This is because the data removal process fulfills our obligations as a data processor as outlined in the European Data legislation introduced in May 2018. Once removed via this process, we therefore have no means of identification or retrieval of your candidate's data.</p>
<h1>Parameters</h1>
<p>No additional parameters</p>
<h1>Deleting by id</h1>
<p>This will remove the exact candidate record(s) with the specified ID(s). Multiple IDs can be specified.</p>
<h2>Example</h2>
<h3>Posted data</h3>
<pre><code>POST https://ws.idibu.com/ws/rest/v1/applicants/request-delete-by-ids?hash=<your hash></code></pre>
<pre><code type="xml">&lt;?xml version="1.0"?&gt;
&lt;idibu&gt;
    &lt;ids&gt;
        &lt;id&gt;12345&lt;/id&gt;
        &lt;id&gt;67890&lt;/id&gt;
    &lt;/ids&gt;
&lt;/idibu&gt;
</code></pre>
<h3>Response</h3>
<pre><code type="xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
  &lt;response&gt;
    &lt;message&gt;Applicants queued for deletion&lt;/message&gt;
  &lt;/response&gt;
  &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
<h1>Deleting by email address</h1>
<p>This will remove all candidate records that hold the specified `FROM` email. Multiple addresses can be specified.</p>
<h2>Example</h2>
<h3>Posted data</h3>
<pre><code>POST https://ws.idibu.com/ws/rest/v1/applicants/request-delete-by-emails?hash=<your hash></code></pre>
<pre><code type="xml">&lt;?xml version="1.0"?&gt;
&lt;idibu&gt;
    &lt;emails&gt;
        &lt;email&gt;example@idibu.com&lt;/email&gt;
        &lt;email&gt;another-example@idibu.com&lt;/email&gt;
     &lt;/emails&gt;
&lt;/idibu&gt;
</code></pre>
<h3>Response</h3>
<pre><code type="xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
  &lt;response&gt;
    &lt;message&gt;Applicants queued for deletion&lt;/message&gt;
  &lt;/response&gt;
  &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
</details>
