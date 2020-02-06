<p>idibu provides intelligent mappings for most of the industry and location related extra fields, thus removing the need to send this data. Whenever an extra field is mapped internally, if this data isn&#39;t present in the payload our system will try to match the corresponding core field value to a value in an extra field.</p>
<p>Our system will return a warning about this, but this won&#39;t prevent the posting unless another kind of error is present:</p>
<pre>
<code>
&lt;!-- ... --&gt;
&nbsp;&nbsp;&nbsp;&lt;extrafield name=&quot;idibu_pcode&quot;&gt;EC1A&lt;/extrafield&gt;
&nbsp;&nbsp;&lt;/board&gt;
&nbsp;&nbsp;&lt;board id=&quot;10&quot;&gt;
&nbsp;&nbsp;&nbsp;&lt;duration days=&quot;14&quot;&gt;&lt;/duration&gt;
&nbsp;&nbsp;&nbsp;&lt;!-- removed extra field Reed_InSec --&gt;
&nbsp;&nbsp;&nbsp;&lt;extrafield name=&quot;reed_location&quot;&gt;38&lt;/extrafield&gt;
&nbsp;&nbsp;&nbsp;&lt;extrafield name=&quot;reed_cboListingType&quot;&gt;1&lt;/extrafield&gt;
&nbsp;&nbsp;&nbsp;&lt;extrafield name=&quot;reed_hidesal&quot;&gt;1&lt;/extrafield&gt;
&nbsp;&nbsp;&lt;/board&gt;
&lt;!-- ... --&gt;
</code></pre>
<p>The response from the API will contain something like this:</p>
<pre>
<code>
&lt;!-- ... --&gt;
&nbsp;&nbsp;&lt;warnings&gt;
&nbsp;&nbsp;&nbsp;&lt;warning field=&#39;Reed_InSec&#39; type=&#39;doubleSelect&#39; boardid=&#39;10&#39;&gt;Field &#39;Reed_InSec&#39; was missing from the payload, but was mapped internally by the system&lt;/warning&gt;
&nbsp;&nbsp;&lt;/warnings&gt;
&lt;!-- ... --&gt;
&lt;/idibu&gt;
</code></pre>
