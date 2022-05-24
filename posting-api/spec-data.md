<p><strong>Different posting destinations require unique data to be sent through to them, for example their own specific sector list or qualification levels.</strong></p>
<p>Our posting API works to understand what extra field data you have sent through, and if anything is missing it will request it via the <a href="https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/pcp.md">PCP</a>.</p>

<p>When using the XML API you may need to be sending job board extra field data depending on how you plan to integrate. These two services provide a listing of job boards your account is subscribed to as well as individual board listings showing extra field items and their values.</p>

<p><strong>Before reading further, please consult <a href="https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/board-specific-fields.md" target="_blank">the following article</a> for information about obtaining the data.</strong></p>

<p>Job board-specific data is provided in the <code>posts</code> section of the XML; each job board's data then goes under the <code>board</code> tag. A simple extra field section for a job board would look like this:</p>
<pre>
&lt;posts&gt;
&nbsp;&nbsp;&lt;board id=&quot;77&quot;&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;duration days=&quot;7&quot; /&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;extrafield name=&quot;auto_StartDate&quot;&gt;13 feb 2009&lt;/extrafield&gt;
&nbsp;&nbsp;&lt;/board&gt;
&lt;/posts&gt;

</pre>
<p>Notice the duration tag - it is non required, however possible values will be shown when you access board&#39;s details using the discovery services. If no duration is provided, user will be prompted to add it via PCP link of a delayed posting.</p>
<p>The idibu system has a number of different extra field types, here are some examples:</p>
<h1>
	Text and Text Area Fields</h1>
<pre>

&lt;extrafield name=&quot;ITjb_skilss&quot;&gt;VB, Java, C#&lt;/extrafield&gt;
</pre>
<h1>
	Select</h1>
<pre>
&lt;extrafield name=&quot;js_Country&quot;&gt;GBR&lt;/extrafield&gt;
</pre>
<h1>
	Multi Select</h1>
<p>Should generate an array, even when it has only 1 item. Only valid format is with the item tags:</p>
<pre>

&lt;extrafield name=&quot;auto_Category&quot;&gt;
&nbsp;&nbsp;&lt;item id=&quot;7206&quot; /&gt;
&nbsp;&nbsp;&lt;item id=&quot;7207&quot; /&gt;
&nbsp;&nbsp;&lt;item id=&quot;7208&quot; /&gt;
&nbsp;&nbsp;&lt;item id=&quot;7211&quot; /&gt;
&lt;/extrafield&gt;
</pre>
<h1>
	Double Select</h1>
<pre>
&lt;extrafield name=&quot;M_dabse&quot; parent=&quot;157&quot;&gt;
&nbsp;&nbsp;&lt;item id=&quot;78&quot; /&gt;
&lt;/extrafield&gt;
</pre>
<h1>
	Double Multi Select</h1>
<p>The first selection is a single dropdown, the second is a multi-select:</p>
<pre>
&lt;extrafield name=&quot;M_CatOpp&quot; parent=&quot;11454&quot;&gt;
&nbsp;&nbsp;&lt;item id=&quot;6&quot; /&gt;
&nbsp;&nbsp;&lt;item id=&quot;11752&quot; /&gt;
&nbsp;&nbsp;&lt;item id=&quot;11800&quot; /&gt;
&lt;/extrafield&gt;
</pre>
<h1>
	Hidden Fields</h1>
<p>Those fields should be ignored by the developers linking their applications to idibu&#39;s API. Those &quot;hidden&quot; fields are fed with data from the dynamic core fields.</p>

<h1>Duration Fields</h1>
Most of your boards will have an additional, duration field, among other extra fields. Possible values can be found in the webservice and the field is required if you'd like to post without PCP. You just need to provide the amount of days your post should be live from the selection available on a per board basis. 
<pre>
&lt;duration days=&quot;7&quot; /&gt;
</pre>
<a href="https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/dyn-vars.md">Continue reading here to learn about dynamic core fields</a>

