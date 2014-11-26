<p><strong>Different posting destinations require unique data to be sent through to them, for example their own specific sector list or qualification levels.</strong></p>
<p>API v3 works to understand what extra field data you have sent through, and if anything is missing it will request it via the <a href="https://github.com/oneworldmarket/idibu-api/blob/master/api-v3/pcp.md">PCP</a>.</p>

<p>When using the XML API you may need to be sending job board extra field data depending on how you plan to integrate. These two services provide a listing of job boards your account is subscribed to as well as individual board listings showing extra field items and their values.</p>
<h1>
	List of Job Boards</h1>
<pre>
<code>http://ws.idibu.com/clients/json.php?class=Portal&action=UserPortal&format=XML&list=subscribed&hash=[INSERT LOGIN HASH HERE]</code></pre>
<p>The valid values for the list parameter are: all, subscribed, unsubscribed.</p>
<p>The properties of the board tag are:</p>
<ul>
	<li>
		id - board id</li>
	<li>
		published &ndash; should be set to &#39;true&#39; if the board is active</li>
	<li>
		allows_html &ndash; if set you can use html in the description</li>
	<li>
		last_modified &ndash; date the board was last updated</li>
	<li>
		subscribed &ndash; a user should only post to the boards they are subscribed to</li>
</ul>
<h1>
	Get Board Data</h1>
<pre>
<code>http://ws.idibu.com/clients/json.php?class=Portal&action=showData&boardID=10&format=XML&hash=[INSERT LOGIN HASH HERE]&profileID=[SENDER ID HERE]</code></pre>
<p>You have to change the boardID parameter to match the board you want to fetch data for, the list of valid ids is fetched from the previous list. ProfileID will be significant for selected boards (i.e. Linkedin) where the extrafields differ based on user&#39;s logins.</p>

<p><strong>Different posting destinations require unique data to be sent through to them, for example their own specific sector list or qualification levels.</strong></p>
<p>API v3 works to understand what extra field data you have sent through, and if anything is missing it will request it via the <a href="https://github.com/oneworldmarket/idibu-api/blob/master/api-v3/pcp.md">PCP</a>.</p>

<p>When using the XML API you may need to be sending job board extra field data depending on how you plan to integrate. These two services provide a listing of job boards your account is subscribed to as well as individual board listings showing extra field items and their values.</p>
<h1>
	List of Job Boards</h1>
<pre>
<code>http://ws.idibu.com/clients/json.php?class=Portal&action=UserPortal&format=XML&list=subscribed&hash=[INSERT LOGIN HASH HERE]</code></pre>
<p>The valid values for the list parameter are: all, subscribed, unsubscribed.</p>
<p>The properties of the board tag are:</p>
<ul>
	<li>
		id - board id</li>
	<li>
		published &ndash; should be set to &#39;true&#39; if the board is active</li>
	<li>
		allows_html &ndash; if set you can use html in the description</li>
	<li>
		last_modified &ndash; date the board was last updated</li>
	<li>
		subscribed &ndash; a user should only post to the boards they are subscribed to</li>
</ul>
<h1>
	Get Board Data</h1>
<pre>
<code>http://ws.idibu.com/clients/json.php?class=Portal&action=showData&boardID=10&format=XML&hash=[INSERT LOGIN HASH HERE]&profileID=[SENDER ID HERE]</code></pre>
<p>You have to change the boardID parameter to match the board you want to fetch data for, the list of valid ids is fetched from the previous list. ProfileID will be significant for selected boards (i.e. Linkedin) where the extrafields differ based on user&#39;s logins.</p>

<p>The extra field data is contained within the &lt;board&gt; tag which also contains the id of the board you are posting to (again, refer to Web Services section to find the id&#39;s for your boards).</p>
<p>A simple extra field section for a job board would look like this:</p>
<pre>

&lt;board id=&quot;77&quot;&gt;
&nbsp;&nbsp;&lt;duration days=&quot;7&quot; /&gt;
&nbsp;&nbsp;&lt;extrafield name=&quot;auto_StartDate&quot;&gt;13 feb 2009&lt;/extrafield&gt;
&lt;/board&gt;

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
<a href="https://github.com/oneworldmarket/idibu-api/blob/master/api-v3/dyn-vars.md">Continue reading here to learn about dynamic core fields</a>
