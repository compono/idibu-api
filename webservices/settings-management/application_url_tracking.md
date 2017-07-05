<p>This method used to set tracking parameters when using application URL method applying. For more information about tracking parameters, please refer to <a href="http://v2-docs.idibu.com/article/52-application-url-source-tracking" target="_blank">this article.</a></p>

<h1>Setting the tracking parameters</h1>

<h2>Request</h2>

<code>POST http://ws.idibu.com/ws/rest/v1/tracking?hash=<your hash></code>

<pre type="xml">
&lt;parameters&gt;
  &lt;board&gt;board-parameter&lt;/board&gt;
  &lt;job&gt;job-parameter&lt;/job&gt;
&lt;/parameters&gt;
</pre>
<br/>
- The <code>board</code> parameter is used to set the name of the parameter used for tracking the source (job board). By default, this parameter will contain a code from <a href="http://www.idibu.com/clients/?class=Portal&action=ListBIDs" target="_blank">this list</a>.
- The <code>job</code> parameter is used to set the name of the Job ID parameter. This parameter will contain a URL-safe-base64 encoded unique ID of the job.

<h1>Obtaining the tracking parameters</h1>

<h2>Request</h2>

<code>GET http://ws.idibu.com/ws/rest/v1/tracking?hash=<your hash></code>
