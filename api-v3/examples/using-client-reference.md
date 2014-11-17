<p>The Client Reference can be used to link the data in our system to data in the client&#39;s system, providing for an easier integration.</p>
<p>Using a client reference makes the use of idibu job ids unnecessary, and allows for easier integration between idibus&#39; Aptrack and the client applicant tracking system by sending the client reference in the Aptrack applicant email metadata (please check the <a href="/docs/applicant-tracking-metadata">reference page</a> to see the information information is sent).</p>
<h1>
	Providing a client reference</h1>
<p>Using a client reference with our API is as easy as adding the corresponding tag in the requests:</p>
<pre>
<code>
&lt;!-- ... --&gt;
&nbsp;&lt;/config&gt;
&nbsp;&lt;job&gt;
&nbsp;&nbsp;&nbsp;&lt;client_reference&gt;SOM3UNIQUERef&lt;/client_reference&gt;
&nbsp;&nbsp;&nbsp;&lt;sender id=&quot;31000383&quot;&gt;&lt;/sender&gt;
&nbsp;&nbsp;&nbsp;&lt;title&gt;&lt;![CDATA[Here goes the job title]]&gt;&lt;/title&gt;
&nbsp;&nbsp;&nbsp;&lt;description&gt;&lt;![CDATA[This is a job description can be long]]&gt;&lt;/description&gt;
&lt;!-- ... --&gt;
</code></pre>
<p>The API will recognise and confirm the client reference by returning it in the result message:</p>
<pre>
<code>
&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot; ?&gt;
&lt;idibu&gt;
&nbsp;&lt;job status=&quot;added&quot; id=&quot;31003390&quot; client_reference=&quot;SOM3UNIQUERef&quot;&gt;
&nbsp;&nbsp;&lt;posts&gt;
&nbsp;&nbsp;&nbsp;&lt;posts status=&quot;pending&quot; boardid=&quot;10&quot; queueid=&quot;1802&quot; type=&quot;add&quot; publish=&quot;2011-07-07 00:01&quot; duration=&quot;14&quot; /&gt;
&nbsp;&nbsp;&nbsp;&lt;posts status=&quot;pending&quot; boardid=&quot;41&quot; queueid=&quot;1803&quot; type=&quot;add&quot; publish=&quot;2011-07-07 00:01&quot; duration=&quot;2&quot; /&gt;
&nbsp;&nbsp;&nbsp;&lt;posts status=&quot;pending&quot; boardid=&quot;517&quot; queueid=&quot;1804&quot; type=&quot;add&quot; publish=&quot;2011-07-07 00:01&quot; duration=&quot;2&quot; /&gt;
&nbsp;&nbsp;&lt;/posts&gt;
&nbsp;&lt;/job&gt;
&lt;/idibu&gt;
</code></pre>
<p>Take into account that for adding jobs to the system, unique client references have to be used. If a client reference is sent in an ADD request, and that client reference has been used for a previous job, the system will fail the request with the following error:</p>
<pre>
<code>
&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot; ?&gt;
&lt;idibu&gt;
&nbsp;&lt;log&gt;
&nbsp;&nbsp;&lt;errors&gt;
&nbsp;&nbsp;&nbsp;&lt;error&gt;The Client Reference provided is already in the system, you have to provide a new reference for a new job.&lt;/error&gt;		
&nbsp;&nbsp;&lt;/errors&gt;
&nbsp;&lt;/log&gt;
&lt;/idibu&gt;
</code></pre>
<p>This is considered a critical error, so no PCP is returned.</p>
<h1>
	Managing jobs using the Client Reference</h1>
<p>The client reference can be used to manage the jobs that are already in the system instead of the idibu job id. For instance, once the job has been posted once with a client reference, updating that job is just a matter of changing the request accordingly:</p>
<pre>
&lt;code&gt;
&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot; ?&gt;
&lt;idibu&gt;
&nbsp;&lt;method&gt;UPDATE&lt;/method&gt;
&nbsp;&lt;config&gt;
&nbsp;&nbsp;&nbsp;&lt;show_durations&gt;No&lt;/show_durations&gt;
&nbsp;&nbsp;&nbsp;&lt;lockboards&gt;YES&lt;/lockboards&gt;
&nbsp;&nbsp;&nbsp;&lt;partnerid&gt;yourpartnerid&lt;/partnerid&gt;
&nbsp;&nbsp;&nbsp;&lt;redirecturl&gt;http://www.google.com&lt;/redirecturl&gt;
&nbsp;&nbsp;&nbsp;&lt;validate_level&gt;Warning&lt;/validate_level&gt;
&nbsp;&nbsp;&lt;/config&gt;
&nbsp;&nbsp;&lt;job&gt;
&nbsp;&nbsp;&nbsp;&lt;sender id=&quot;31000383&quot;&gt;&lt;/sender&gt;
&nbsp;&nbsp;&nbsp;&lt;client_reference&gt;SOM3UNIQUERef&lt;/client_reference&gt;
&nbsp;&nbsp;&nbsp;&lt;title&gt;&lt;![CDATA[Here goes the job title]]&gt;&lt;/title&gt;
&lt;!-- ... --&gt;
In this case, if the system finds no quota constrains the results are going to be exactly as above, bar the changed corresponding queue ids:
<pre class="brush:xml">
&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot; ?&gt;
&lt;idibu&gt;
&nbsp;&nbsp;&lt;!-- job id matches the id informed previously by the system --&gt;
&nbsp;&nbsp;&lt;job status=&quot;added&quot; id=&quot;31003390&quot; client_reference=&quot;SOM3UNIQUERef&quot;&gt;
&nbsp;&nbsp;&nbsp;&lt;posts&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;posts status=&quot;pending&quot; boardid=&quot;10&quot; queueid=&quot;1808&quot; type=&quot;add&quot; publish=&quot;2011-07-07 00:01&quot; duration=&quot;14&quot; /&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;posts status=&quot;pending&quot; boardid=&quot;41&quot; queueid=&quot;1809&quot; type=&quot;add&quot; publish=&quot;2011-07-07 00:01&quot; duration=&quot;2&quot; /&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;posts status=&quot;pending&quot; boardid=&quot;517&quot; queueid=&quot;1810&quot; type=&quot;add&quot; publish=&quot;2011-07-07 00:01&quot; duration=&quot;2&quot; /&gt;
&nbsp;&nbsp;&nbsp;&lt;/posts&gt;
&nbsp;&nbsp;&lt;/job&gt;
&lt;/idibu&gt;
</code></pre>
<p>The same thing can be applied to REPOST, QUICKREPOST, DELETE and CANCEL requests: the client reference is a completeent for idibu job ids.</p>
<h1>
	Updating a job&#39;s client reference</h1>
<p>If it is needed to update or change the existing client reference of a job, then it is mandatory to use the idibu job id:</p>
<pre>
<code>
&lt;!-- ... --&gt;
&nbsp;&lt;/config&gt;
&nbsp;&lt;!-- we use the job id provided by idibu --&gt;
&nbsp;&lt;job id=&quot;31003390&quot;&gt;
&nbsp;&nbsp;&lt;sender id=&quot;31000383&quot;&gt;&lt;/sender&gt;
&nbsp;&nbsp;&lt;client_reference&gt;SOM3-New-UNIQUERef&lt;/client_reference&gt;
&nbsp;&nbsp;&lt;title&gt;&lt;![CDATA[Here goes the job title]]&gt;&lt;/title&gt;
&lt;!-- ... --&gt;
</code></pre>
<p>Again, the system will acknowledge the new client reference by returning it in the result message:</p>
<p>For further advice and examples, talk to us on the <a href="/forum">support forum</a>.&nbsp;</p>
