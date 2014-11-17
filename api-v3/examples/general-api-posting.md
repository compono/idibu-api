<p>The example used as a starting point above, is a complete payload that can be used to post. If you post to the API using it, you will get a response similar to this one:</p>
<pre>
<code>
&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot; ?&gt;
&lt;idibu&gt;
&nbsp;&lt;job status=&quot;added&quot; id=&quot;31003367&quot;&gt;
&nbsp;&nbsp;&lt;posts&gt;
&nbsp;&nbsp;&lt;posts status=&quot;pending&quot; boardid=&quot;10&quot; queueid=&quot;1769&quot; type=&quot;add&quot; publish=&quot;2011-07-07 00:01&quot; duration=&quot;14&quot; /&gt;
&nbsp;&nbsp;&lt;posts status=&quot;pending&quot; boardid=&quot;41&quot; queueid=&quot;1770&quot; type=&quot;add&quot; publish=&quot;2011-07-07 00:01&quot; duration=&quot;2&quot; /&gt;
&nbsp;&nbsp;&lt;posts status=&quot;pending&quot; boardid=&quot;517&quot; queueid=&quot;1771&quot; type=&quot;add&quot; publish=&quot;2011-07-07 00:01&quot; duration=&quot;2&quot; /&gt;
&nbsp;&nbsp;&lt;/posts&gt;
&nbsp;&lt;/job&gt;
&nbsp;&lt;log&gt;
&nbsp;&nbsp;&lt;warnings&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;warning type=&quot;short_on_quota&quot;&gt;The account is running out of quota for this profile/user/team for this board (BOARD ID: 517)&lt;/warning&gt;
&nbsp;&nbsp;&lt;/warnings&gt;
&nbsp;&lt;/log&gt;
&lt;/idibu&gt;
</code></pre>
<p><strong>All the ids and URLs shown in the examples response are for illustrative purposes, and using them will the live system will likely result in error.</strong></p>
<p>As you can see from the result, the job has been posted successfully, and the data for the postings is returned. The system returns as well an warning indicating that either the profile used, the team the profile is assigned to, or the parent office is running out of quota for the board with id 517. If you keep posting to this board without increasing quota, eventually you&#39;ll get a result similar to this one:</p>
<pre>
<code>
&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot; ?&gt;
&lt;idibu&gt;
&nbsp;&lt;job status=&quot;delayed&quot; id=&quot;31003369&quot; postingid=&quot;338&quot;&gt;
&nbsp;&nbsp;&lt;postcompletionurl&gt;http://pascal-adpost.idibu.com/cBzfC.html&lt;/postcompletionurl&gt;
&nbsp;&lt;/job&gt;
&nbsp;&lt;log&gt;
&nbsp;&nbsp;&lt;warnings&gt;
&nbsp;&nbsp;&nbsp;&lt;warning type=&quot;no_quota_left&quot;&gt;The account has no quota left for this profile/user/team for this board (BOARD ID: 517)&lt;/warning&gt;
&nbsp;&nbsp;&lt;/warnings&gt;
&nbsp;&lt;/log&gt;
&lt;/idibu&gt;
</code></pre>
<p>Here we can observe two things:</p>
<ol>
	<li>
		The postings are handled atomically. If for whatever reason the system finds a non critical error (In this case, there&#39;s a problem with the quota fro board 517) all postings are withheld together.</li>
	<li>
		We have the first example of a <a href="/docs/posting-completion-page">Post Completion Page</a> (PCP) &quot;http://adpost.idibu.com/cBzfC.html&quot;</li>
</ol>
<p class="p1">In order to finish the posting, first the account administrator needs to solve the quota issue, and the consultant can finish the posting by accessing the <b>PCP</b>.&nbsp;</p>
