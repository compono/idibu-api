<p>The <strong>CANCEL</strong> method allows you to delete from the system both queued posts and job posting pending completion (Those requests that return a <a href="https://github.com/oneworldmarket/idibu-api/blob/master/api-v3/pcp.md">PCP</a>).</p>
<p>You use the ids passed back during the posting process to identify which posts you want to delete. Depending on the results of the posting, you&#39;ll get either queue ids (If the posting was completely successful) or posting ids (If there was a not critical error, and the posting configuration allows for the PCP to be generated.</p>
<p>Take into account that queued posts are usually processed within 5 minutes, if the user is allowed to post directly - this depends on the posting authorization policies in idibu - so they&#39;re more likely to result in a failed attempt to cancel. Job postings do not get deleted until the consultant completes the posting (By accessing the <a href="https://github.com/oneworldmarket/idibu-api/blob/master/api-v3/pcp.md">PCP</a>).</p>
<p>This is an example payload for the cancel request:</p>
<pre><code>
&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot;?&gt;
&lt;idibu&gt;
&nbsp;&lt;method&gt;cancel&lt;/method&gt;
&nbsp;&lt;postqueue&gt;
&nbsp;&nbsp;&lt;queue id=&quot;1079&quot; /&gt;
&nbsp;&nbsp;&lt;queue id=&quot;1023&quot; /&gt;
&nbsp;&lt;/postqueue&gt;
&nbsp;&lt;jobpostings&gt;
&nbsp;&nbsp;&lt;posting id=&quot;229&quot; /&gt;
&nbsp;&nbsp;&lt;posting id=&quot;230&quot; /&gt;
&nbsp;&nbsp;&lt;posting id=&quot;235&quot; /&gt;
&nbsp;&lt;/jobpostings&gt;
&lt;/idibu&gt;
</code></pre>
<p>It allows for cancelling of either postings or queued posts in the same request. You should provide at least one tag with a valid id on it. IDs are provided in the response of a valid request.</p>
<p>When making a cancel request, the system reposts back the results of processing the request. It is possible to get back a message with mixed results, like this:</p>
<pre>
<code>
&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot; ?&gt;
&lt;idibu&gt;
&nbsp;&nbsp;&lt;queue status=&quot;cancelled&quot; id=&quot;1079&quot;&gt;The stated record has been deleted/cancelled&lt;/queue&gt;
&nbsp;&nbsp;&lt;queue status=&quot;failed&quot; id=&quot;1023&quot;&gt;No record with the stated ID was found&lt;/queue&gt;
&nbsp;&nbsp;&lt;posting status=&quot;cancelled&quot; id=&quot;229&quot;&gt;The stated record has been deleted/cancelled&lt;/posting&gt;
&nbsp;&nbsp;&lt;posting status=&quot;cancelled&quot; id=&quot;230&quot;&gt;The stated record has been deleted/cancelled&lt;/posting&gt;
&nbsp;&nbsp;&lt;posting status=&quot;failed&quot; id=&quot;235&quot;&gt;No record with the stated ID was found&lt;/posting&gt;
&lt;/idibu&gt;
</code></pre>
Wherever job board give such opportunity, one can also <a href="https://github.com/oneworldmarket/idibu-api/blob/master/api-v3/delet-jobs.md">delete a job</a>.
