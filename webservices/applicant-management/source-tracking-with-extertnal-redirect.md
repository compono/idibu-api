_**This document is outdated. Please refer to the new version [HERE](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/applicant-management/applicant-management-webservice.md).**_

<details>
 <summary><i>Show me anyway</i></summary>

This webservice allows you to benefit from the functionality described <a href="http://support.idibu.com/default_import/Knowledgebase/Article/View/201/0/application-url-source-tracking" target="_blank">here</a> outside idibu.

setting tracking parameters (tracking will be enabled if at least one is set to a non-empty value):
	<br />	<br />
	<code>
POST /ws/rest/v1/tracking?hash=[client-hash]
</code></p>
<h2>
	Response</h2>
<pre><code type="xml">
&lt;parameters&gt;
  &lt;board&gt;board-parameter&lt;/board&gt;
  &lt;job&gt;job-parameter&lt;/job&gt;
&lt;/parameters&gt;
</code></pre>
<pre>
    checking tracking parameters:	<br />
    <code>
GET /ws/rest/v1/tracking?hash=[client-hash]
</code></p>
</details>
