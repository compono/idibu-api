<p>You may send in requests to delete the adverts for a particular job. In order to delete adverts, a valid <a href="https://github.com/oneworldmarket/idibu-api/blob/master/api-v3/jobidvsjobref.md">Job ID or Client Reference</a> needs to be provided.</p>
<h1>
	Deleting all posts for a job</h1>
<p>This is an example XML file for a delete request:</p>
<pre>
<code>
&lt;IDIBU&gt;
&nbsp;&nbsp;&lt;METHOD&gt;DELETE&lt;/METHOD&gt;
&nbsp;&nbsp;&lt;JOB ID=&quot;425&quot; /&gt;
&lt;/IDIBU&gt;
</code></pre>
<p>This request will delete all successful postings for that job (Note, this can only be performed on job boards that support the delete function). Take into account that delete takes precedence over adding a job, so if the method tag is set to &quot;delete&quot; whatever is in the request that is not related to the delete request will not be processed.</p>
<h2>
	Deleting specific posts for a job</h2>
<p>If you want to delete postings for 1 or more particular boards for a certain job, you can do that using an XML format as below:</p>
<pre>
<code>
&lt;IDIBU&gt;
&lt;METHOD&gt;DELETE&lt;/METHOD&gt;
&nbsp;&lt;JOB ID=&quot;31002847&quot;&gt;
&nbsp;&lt;POSTS&gt;
&nbsp;&nbsp;&lt;BOARD ID=&quot;10&quot; /&gt;
&nbsp;&nbsp;&lt;BOARD ID=&quot;54&quot; /&gt;
&nbsp;&lt;/POSTS&gt;
&nbsp;&lt;/JOB&gt;
&lt;/IDIBU&gt;
</code></pre>
<h1>
	Response messages for delete requests</h1>
<p>Below you will find various examples of the possible system response messages:</p>
<h2>
	Succesful delete request message</h2>
<pre>
<code>
&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot;?&gt;
&lt;IDIBU&gt;
&lt;JOB ID=&quot;31002847&quot;&gt;
&lt;POST STATUS=&quot;PENDING&quot; TYPE=&quot;Del&quot; BOARDID=&quot;54&quot; REMOTEID=&quot;something&quot; QUEUEID=&quot;847&quot;&gt;Job was posted for deletion to this board.&lt;/POST&gt;&lt;/JOB&gt;
&lt;/IDIBU&gt;
</code></pre>
<h2>
	No posts were found suitable for delete</h2>
<pre>
<code>
<?xml version="1.0" encoding="UTF-8"?>
&lt;IDIBU&gt;
&lt;JOB ID=&quot;31002847&quot;&gt;
&lt;ERROR&gt;No posts suitable for deletion were found for the stated job&lt;/ERROR&gt;&lt;/JOB&gt;
&lt;/IDIBU&gt;
</code></pre>
<h2>
	Mixed response when board ids are provided</h2>
<pre>
<code>
&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot;?&gt;
&lt;IDIBU&gt;
&lt;JOB ID=&quot;31002847&quot;&gt;
&lt;POST BOARDID=&quot;10&quot; STATUS=&quot;FAILED&quot;&gt;No posts suitable for deletion were found for this board&lt;/POST&gt;
&lt;POST STATUS=&quot;PENDING&quot; TYPE=&quot;Del&quot; BOARDID=&quot;54&quot; REMOTEID=&quot;something&quot; QUEUEID=&quot;853&quot;&gt;Job was posted for deletion to this board.&lt;/POST&gt;&lt;/JOB&gt;
&lt;/IDIBU&gt;
</code>
You can also delete all posts from a single reference:
<h2>
	Reference based delete</h2>
<pre>
<code>
&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot;?&gt;
&lt;idibu&gt;
	&lt;method&gt;delete&lt;/method&gt;
	&lt;job ref=&quot;JO-1404-7731&quot; all=&quot;yes&quot;&gt;&lt;/job&gt;
&lt;/idibu&gt;
</code></pre>
You can also provide multiple references for many jobs with one call usin ;!; sepator
<pre>
<code>
&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot;?&gt;
&lt;idibu&gt;
	&lt;method&gt;delete&lt;/method&gt;
	&lt;job ref=&quot;JO-1404-7731;!;JO-1404-7732;!;JO-1404-7733&quot; all=&quot;yes&quot;&gt;&lt;/job&gt;
&lt;/idibu&gt;
</code></pre>

<?xml version="1.0" encoding="UTF-8"?><idibu><method>delete</method><job ref="JO-1404-7731" all="yes"></job></idibu>
</pre>
You can also delete based on <a href="https://github.com/oneworldmarket/idibu-api/blob/master/api-v3/ref-based-delete.md">Client reference</a>,
