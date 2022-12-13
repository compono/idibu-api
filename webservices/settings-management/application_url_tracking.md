<p>This method used to set tracking parameters when using application URL method applying. For more information about tracking parameters, please refer to <a href="http://v2-docs.idibu.com/article/52-application-url-source-tracking" target="_blank">this article.</a></p>

<h1>Setting the tracking parameters</h1>

<h2>Request</h2>

<code>POST https://ws.idibu.com/ws/rest/v1/tracking?hash=<your hash></code>

<pre type="xml">
&lt;parameters&gt;
  &lt;board&gt;board-parameter&lt;/board&gt;
  &lt;job&gt;job-parameter&lt;/job&gt;
&lt;/parameters&gt;
</pre>

- <code>board</code> is used to set the name of the parameter used for tracking the source (job board). You can obtain the code (that will be sent as the value of this parameter) for each Portal through the <code>bid</code> field from the [Get Board Data](https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/board-specific-fields.md) response.
- <code>job</code> is used to set the name of the Job ID parameter. This parameter will contain a URL-safe-base64 encoded unique ID of the Job (refer to the [Job Management Webservice](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/job-management/job-management-webservice.md)).

<h1>Obtaining the tracking parameters</h1>

<h2>Request</h2>

<code>GET https://ws.idibu.com/ws/rest/v1/tracking?hash=<your hash></code>
