<p>The <strong>QUICKREPOST</strong> method allows you to instantaneously repost data that is already in the system, and has successfully been previously posted to at least one destination. In the payload the job id has to be passed as a parameter to the job tag.</p>
<p>You can explicitly state which destinations you want to quick repost the data back to, or leave this blank - in which case the system will re-broadcast to all previous destinations.</p>
<p>This is an example payload for the QUICKREPOST request:</p>
<pre>
<code>
<?xml version="1.0" encoding="UTF-8"?>
&lt;idibu&gt;
&nbsp;&nbsp;&lt;method&gt;quickrepost&lt;/method&gt;
&nbsp;&nbsp;&lt;job id=&quot;31002766&quot;&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;board id=&quot;10&quot; /&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;board id=&quot;517&quot; /&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;board id=&quot;520&quot; /&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;board id=&quot;86&quot; /&gt;
&nbsp;&nbsp;&lt;/job&gt;
&lt;/idibu&gt;
</code></pre>
<p>Depending on the system configuration and the previous results of posting the job, you can get a response with mixed results:</p>
<pre>
<code>
&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot; ?&gt;
&lt;idibu&gt;
&nbsp;&lt;JOB ID=&quot;31002766&quot;&gt;
&nbsp;&nbsp;&lt;POST STATUS=&quot;FAILED&quot; BOARDID=&quot;520&quot; REASON=&quot;not-subscribed&quot;&gt;This account is not subscribed to the stated board.&lt;/POST&gt;
&nbsp;&nbsp;&lt;POST STATUS=&quot;PENDING&quot; TYPE=&quot;ADD&quot; QUICKREPOST=&quot;YES&quot; BOARDID=&quot;10&quot; QUEUEID=&quot;54263&quot; PUBLISH=&quot;2011-02-25 16:00&quot; DURATION=&quot;7&quot; /&gt;
&nbsp;&nbsp;&lt;POST STATUS=&quot;FAILED&quot; BOARDID=&quot;86&quot; REASON=&quot;no-post&quot;&gt;This job hasn&#39;t been previously succesfully posted to this board.&lt;/POST&gt;
&nbsp;&nbsp;&lt;POST STATUS=&quot;FAILED&quot; BOARDID=&quot;517&quot; REASON=&quot;no-quota&quot;&gt;The stated board has no quota available&lt;/POST&gt;
&nbsp;&lt;/JOB&gt;
&lt;/idibu&gt;
</code></pre>
<p>The different values for the REASON parameter and their meaning are in the example XML. It can happen that there are critical errors with the account or the job, in which case the result XML will be something like this:</p>
<pre>
<code>
&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot; ?&gt;
&lt;idibu&gt;
&nbsp;&lt;JOB ID=&quot;31002766&quot;&gt;
&nbsp;&nbsp;&lt;ERROR TYPE=&quot;credit&quot;&gt;This is a pay-per-post account, and it has no credits left. Please ask your account administrator to contact idibu. Thanks.&lt;/ERROR&gt;
&nbsp;&nbsp;&lt;ERROR TYPE=&quot;boards&quot;&gt;There are no subscribed boards. Please contact your account administrator&lt;/ERROR&gt;
&nbsp;&nbsp;&lt;ERROR TYPE=&quot;posts&quot;&gt;No posts suitable for reposting were found for this job.&lt;/ERROR&gt;
&nbsp;&lt;/JOB&gt;
&lt;/idibu&gt;
</code></pre>
<p>All the different values for the type parameter are in the example XML.</p>
<p>When there&#39;s a critical error either with the account or the job, any combination of the 3 errors can be generated.</p>
You can also <a href="https://github.com/oneworldmarket/idibu-api/blob/master/api-v3/canceling-pend-posts.md">cancel a pending job</a>.
