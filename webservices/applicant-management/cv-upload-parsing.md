You can upload applicant data into idibu.

This is useful if you want legacy applicant data to be available via our local search, or you have arranged to have fully parsed data handed back to you.

<p>Method imports CV into the idibu&nbsp;local search database.</p>
<p>Use the job id and reference to define which job the applicant will be attached to, these are required fields.</p>
<p>Don&#39;t worry if you can&#39;t supply email or first/last names, we&#39;ll try to grab those from the CV itself.</p>
<p>Please note that CV contents should be base64 encoded, file name shouldn&#39;t contain any extra symbols</p>
<div>
	<h1 class="p3">
		Example</h1>
	<h2>
		Request</h2>
	<pre>
<code type="xml">
&lt;idibu&gt; 
&lt;job&gt; 
&lt;id&gt; 33028649 &lt;/id&gt; 
&lt;reference&gt; TSTJOBREF &lt;/reference&gt; 
&lt;/job&gt; 
&lt;cv&gt; 
&lt;contents&gt; cv contents base64 encoded here &lt;/contents&gt; 
&lt;name&gt; some_file.txt &lt;/name&gt; 
&lt;/cv&gt; 
&lt;/idibu&gt;
&lt;/code&gt;
&lt;/pre&gt;
	&lt;h2&gt;
		Response&lt;/h2&gt;
	&lt;pre&gt;
&lt;code type=&quot;xml&quot;&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt; 
&lt;response&gt; CV uploaded &lt;/response&gt; 
&lt;status&gt; success &lt;/status&gt; 
&lt;/idibu&gt;
</code></pre>
</div>
<p>&nbsp;</p>
