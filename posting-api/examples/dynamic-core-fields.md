<p>One of the feature introduced in this API are Dynamic Core Fields.</p>
<p>These are a set of fields that are not mandatory, and will not result in errors if not sent. If present, they will be used to populate related extra fields for the present boards. Let`s assume some fields are removed from the original request (We are sending the data in a way that we`ll get a PCP only if an error is found):</p>
<pre>
<code>
&lt;!-- ... --&gt;
&nbsp;&nbsp;&lt;posts&gt;
&nbsp;&nbsp;&nbsp;&lt;board id=&quot;517&quot;&gt;
                &lt;duration days=&quot;2&quot;&gt;&lt;/duration&gt;
                &lt;extrafield name=&quot;idibudts_cat&quot;&gt;1&lt;/extrafield&gt;
                &lt;!-- removed &quot;app_url_test&quot; --&gt;
                &lt;extrafield name=&quot;idibu_pcode&quot;&gt;EC1A&lt;/extrafield&gt;
&nbsp;&nbsp;&nbsp;&lt;/board&gt;
&nbsp;&nbsp;&nbsp;&lt;board id=&quot;10&quot;&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;duration days=&quot;14&quot;&gt;&lt;/duration&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;extrafield name=&quot;Reed_InSec&quot; parent=&quot;52&quot;&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;item id=&quot;56&quot; /&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;/extrafield&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;extrafield name=&quot;reed_location&quot;&gt;38&lt;/extrafield&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;extrafield name=&quot;reed_cboListingType&quot;&gt;1&lt;/extrafield&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;extrafield name=&quot;reed_hidesal&quot;&gt;1&lt;/extrafield&gt;
&nbsp;&nbsp;&nbsp;&lt;/board&gt;
&nbsp;&nbsp;&nbsp;&lt;board id=&quot;41&quot;&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;duration days=&quot;2&quot;&gt;&lt;/duration&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;extrafield name=&quot;JS_Industries&quot;&gt;IT&lt;/extrafield&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;extrafield name=&quot;JS_Salary&quot;&gt;No benefits&lt;/extrafield&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;extrafield name=&quot;jobsiteStartDate&quot;&gt;Immediate&lt;/extrafield&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;extrafield name=&quot;jobsite_anyjobs&quot;&gt;E&lt;/extrafield&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;!-- removed &quot;JS_url_app&quot; --&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;extrafield name=&quot;js_oloc&quot;&gt;Greater London Area&lt;/extrafield&gt;
&nbsp;&nbsp;&nbsp;&lt;/board&gt;
&nbsp;&nbsp;&lt;/posts&gt;
&lt;!-- ... --&gt;
</code></pre>
<p>This will get us a response like this:</p>
<pre>
<code>
&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot; ?&gt;
&lt;idibu&gt;
&nbsp;&lt;job status=&quot;added&quot; id=&quot;31003380&quot;&gt;
&nbsp;&nbsp;&lt;posts&gt;
&nbsp;&nbsp;&nbsp;&lt;posts status=&quot;pending&quot; boardid=&quot;10&quot; queueid=&quot;1787&quot; type=&quot;add&quot; publish=&quot;2011-07-07 00:01&quot; duration=&quot;14&quot; /&gt;
&nbsp;&nbsp;&nbsp;&lt;posts status=&quot;pending&quot; boardid=&quot;41&quot; queueid=&quot;1788&quot; type=&quot;add&quot; publish=&quot;2011-07-07 00:01&quot; duration=&quot;2&quot; /&gt;
&nbsp;&nbsp;&nbsp;&lt;posts status=&quot;pending&quot; boardid=&quot;517&quot; queueid=&quot;1789&quot; type=&quot;add&quot; publish=&quot;2011-07-07 00:01&quot; duration=&quot;2&quot; /&gt;
&nbsp;&nbsp;&lt;/posts&gt;
&nbsp;&lt;/job&gt;
&nbsp;&lt;log&gt;
&nbsp;&nbsp;&lt;warnings&gt;
&nbsp;&nbsp;&nbsp;&lt;warning field=&#39;app_url_test&#39; type=&#39;text&#39; boardid=&#39;517&#39;&gt;Field &#39;app_url_test&#39; is missing, an empty string, or contains only whitespace.&lt;/warning&gt;
&nbsp;&nbsp;&nbsp;&lt;warning field=&#39;JS_url_app&#39; type=&#39;text&#39; boardid=&#39;41&#39;&gt;Field &#39;JS_url_app&#39; is missing, an empty string, or contains only whitespace.&lt;/warning&gt;
&nbsp;&nbsp;&lt;/warnings&gt;
&nbsp;&nbsp;&lt;/log&gt;
&lt;/idibu&gt;
</code></pre>
<p>As you can see, the job has been posted, but we received warning about the missing extra fields. As those two fields are linked to the dynamic core field app_url, we can suppress the warning by modifying the request like this:</p>
<pre>
<code>
&lt;!-- ... --&gt;
&nbsp;&lt;job&gt;
&nbsp;&nbsp;&lt;sender id=&quot;31000383&quot;&gt;&lt;/sender&gt;
&nbsp;&nbsp;&lt;!-- app_url DCF below. Order of core fields is not critical --&gt;
&nbsp;&nbsp;&lt;app_url&gt;http://somesite.com/example_app_url.htm&lt;/app_url&gt;
&nbsp;&nbsp;&lt;title&gt;&lt;![CDATA[Here goes the job title]]&gt;&lt;/title&gt;
&nbsp;&nbsp;&lt;description&gt;&lt;![CDATA[This is a job description can be long]]&gt;&lt;/description&gt;
&nbsp;&nbsp;&lt;reference&gt;2080&lt;/reference&gt;
&nbsp;&nbsp;&lt;startdate&gt;2011-07-07&lt;/startdate&gt;
&lt;!-- ... --&gt;
</code></pre>
<p>In this case, the value of Dynamic Core Field&nbsp;<strong>app_url</strong> will be pre populated to both of the destination specific extra fields&nbsp;<strong>app_url_test</strong> and <strong>JS_url_app</strong>, thus suppressing the errors.</p>
<p>It is possible to use both the dynamic core fields and still sent values for some of the corresponding extra fields. The extra field value will take precedence over the value of the DCF, allowing for per posting desitnation customization.</p>
<p><strong>The extra fields used for this example can be different than those linked to the stated DCF. For current and accurate data, please check the <a href="/docs/job-board-data">discovery service</a> for the corresponding boards.</strong></p>
