<p>Method sets quota type for portal.</p>
<p>To set quotas you need to POST <code>data</code> parameter containing an xml. XML should contain quotas type and additional parameters related to it.</p>
<p>Quotas type can be either <code>slots</code> or <code>period</code>:</p>
<ul>
	<li>For <code>slots</code> no additional paramaters are needed.</li>
	<li>For <code>period</code> mandatory parameters are:
		<ul>
			<li><strong><code>period</code></strong> - quotas period. Possible values are:
				<ul>
					<li><code>Week</code></li>
					<li><code>Month</code></li>
					<li><code>Quarter</code></li>
					<li><code>Year</code></li>
				</ul></li>
			<li><strong><code>base</code></strong> - How to deduct posting credits?. Possible values are:
				<ul>
					<li><code>Post</code> - Use only one posting credit no matter how long the job is posted out for.</li>
					<li><code>Week</code> - Use up a posting credit for every week the job is posted out.</li>
				</ul></li>
			<li><strong><code>reset</code></strong> - What to do when the quotas reset. Possible values are:
				<ul>
					<li><code>Ignore</code> - Ignore any unused quota.</li>
					<li><code>Carry</code> - Carry over unused quota to the next period.</li>
				</ul></li>
			<li><strong><code>month-renewal</code></strong> - mandatory only if <code>period</code> is Month. Value should be in 2-digit format and should represent a day of month. Examples: 01, 05, 11, 29, 31.</li>
			<li><strong><code>year-renewal</code></strong> - mandatory only if <code>period</code> is Year. Value should be in <code>dd-mm</code> format, where <code>dd</code> - 2-digit number representing a day, <code>mm</code> - 2-digit number representing a month.</li>
		</ul>
	</li>
</ul>
<h1>Parameters</h1>
<p>No additional parameters</p>
<h1>Example</h1>
<h2>Posted data</h2>
<pre><code>POST http://ws.idibu.com/ws/rest/v1/quotas/517/new?hash=YOUR_HASH</code></pre>
<pre><code type="xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu&gt;
    &lt;type&gt;period&lt;/type&gt;
    &lt;period&gt;Year&lt;/period&gt;
    &lt;year-renewal&gt;20-03&lt;/year-renewal&gt;
    &lt;base&gt;Post&lt;/base&gt;
    &lt;reset&gt;Ignore&lt;/reset&gt;
&lt;/idibu&gt;
</code></pre>
<h2>Response</h2>
<pre><code type="xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
    &lt;response&gt;
        &lt;message&gt;Quotas set&lt;/message&gt;
    &lt;/response&gt;
&lt;/idibu&gt;
</code></pre>
