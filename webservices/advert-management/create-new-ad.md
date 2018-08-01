This method creates a dummy advert. This advert is not going to be posted anywhere, it will just stay in idibu.</p>
Method is useful when you want to import CVs from your hard-drive to idibu. Simply create a new dummy advert using this method and use the returned job ID for upload CVs method (<a href="/docs/add-cv-wsrestv1aptrackadd-cv">/ws/rest/v1/aptrack/add-cv</a>).</p>
</div>
<div>
	<h1 class="p3">
		Example</h1>
	<h2>
		Request</h2>
	<pre>
<code type="xml">
&lt;idibu&gt;
    &lt;job&gt;&lt;title&gt;&lt;/title&gt;
        &lt;reference&gt;JOB_UNIQ_REFERENCE&lt;/reference&gt;
        &lt;description&gt;Job description&lt;/description&gt;
        &lt;sender-id&gt;487&lt;/sender-id&gt;
        &lt;sector-id&gt;5&lt;/sector-id&gt;
        &lt;type&gt;permanent&lt;/type&gt;
    &lt;/job&gt;
&lt;/idibu&gt;
</code>
</pre>
	<h2>
		Response</h2>
	<pre>
<code type="xml">
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
    &lt;response&gt;
        &lt;id&gt;33030026&lt;/id&gt;
    &lt;/response&gt;
    &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
</div>
<p>&nbsp;</p>
