<p>Method sets quota type for portal.</p>
<p>So to set quota type need to POST *data* parameter with xml. XML should contain quotas type and additional params related to that quotas type.</p>
<p>Quotas type can be either *slots* or *period*.</p>
<p>For *slots* no additional paramaters needed.</p>
<p>For *period* mandatory parameters are:</p>
<ul>
	<li>
		period - quotas period. Possible values are: Week, Month, Quarter, Year.</li>
	<li>
		base - How to deduct posting credits?. Possible values are: Post - ``Use *only* one posting credit no matter how long the job is posted out for``, Week - ``Use up a posting credit for every week the job is posted out``</li>
	<li>
		reset - What to do when the quotas reset. Possible values are: Ignore - ``Ignore any unused quota``, Carry - `Carry over unused quota to the next period``.</li>
	<li>
		month-renewal - mandatory only if *period* is Month. Value should be in 2-digit format and should represent a day of month. Examples: 01, 05, 11, 29, 31.</li>
	<li>
		year-renewal - mandatory only if *period* is Year. Value should be in format *dd-mm*, where dd - 2-digit format of day, mm - 2-digit format of month.</li>
</ul>
<h1>
	Parameters</h1>
<p>No additional parameters</p>
<h1>
	Example</h1>
<h2>
	Posted data</h2>
<pre>
<code>
POST http://ws.idibu.com/ws/rest/v1/quotas/517/new?hash=<your hash>
</code></pre>
<pre>
<code type="xml">
&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu&gt;
    &lt;type&gt;period&lt;/type&gt;
    &lt;period&gt;Year&lt;/period&gt;
    &lt;year-renewal&gt;&lt;/year-renewal&gt;&lt;year-renewal&gt;&lt;/year-renewal&gt;&lt;year-renewal&gt;20-03&lt;/year-renewal&gt;&lt;base /&gt;Post
    &lt;reset&gt;Ignore&lt;/reset&gt;
&lt;/idibu&gt;
&lt;/code&gt;&lt;/pre&gt;
&lt;h2&gt;
	Response&lt;/h2&gt;
&lt;pre&gt;
&lt;code type=&quot;xml&quot;&gt;
&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
    &lt;response&gt;
        &lt;message&gt;Quotas set&lt;/message&gt;
    &lt;/response&gt;
&lt;/idibu&gt;
</code></pre>
