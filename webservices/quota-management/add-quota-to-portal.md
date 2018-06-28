<p>Method sets quota type for portal.</p>
<p>To set quotas you need to POST <code>data</code> parameter containing an xml. XML should contain quotas type and additional parameters related to it.</p>
<p>Quotas type can be either <code>slots</code> or <code>period</code>:</p>
<ul>
	<li>For <code>slots</code> available parameters are:
		<ul>
			<li><strong><code>budget-type</code></strong> - optional; period for which the budget is allocated. Possible values are:
				<ul>
					<li><code>month</code> - every month of using the job board costs as much as <strong><code>budget-amount</code></strong> indicates.</li>
					<li><code>year</code> - every year of using the job board costs as much as <strong><code>budget-amount</code></strong> indicates.</li>
				</ul>
			</li>
			<li><strong><code>budget-amount</code></strong> - optional; the available budget (decimal).</li>
			<li><strong><code>slots-available</code></strong> - optional; the amount of slots (integer).</li>
		</ul>
	</li>
	<li>For <code>period</code> available parameters are:
		<ul>
			<li><strong><code>period</code></strong> - quotas period. Possible values are:
				<ul>
					<li><code>Week</code></li>
					<li><code>Month</code></li>
					<li><code>Quarter</code></li>
					<li><code>Year</code></li>
				</ul>
			</li>
			<li><strong><code>base</code></strong> - How to deduct posting credits?. Possible values are:
				<ul>
					<li><code>Post</code> - Use only one posting credit no matter how long the job is posted out for.</li>
					<li><code>Week</code> - Use up a posting credit for every week the job is posted out.</li>
				</ul>
			</li>
			<li><strong><code>reset</code></strong> - What to do when the quotas reset. Possible values are:
				<ul>
					<li><code>Ignore</code> - Ignore any unused quota.</li>
					<li><code>Carry</code> - Carry over unused quota to the next period.</li>
				</ul>
			</li>
			<li><strong><code>month-renewal</code></strong> - mandatory only if <code>period</code> is Month. Value should be in 2-digit format and should represent a day of month. Examples: 01, 05, 11, 29, 31.</li>
			<li><strong><code>year-renewal</code></strong> - mandatory only if <code>period</code> is Year. Value should be in <code>dd-mm</code> format, where <code>dd</code> - 2-digit number representing a day, <code>mm</code> - 2-digit number representing a month.</li>
			<li><strong><code>budget-type</code></strong> - optional; period for which the budget is allocated. Possible values are:
				<ul>
					<li><code>payperpost</code> - each post costs as much as <strong><code>budget-amount</code></strong> indicates.</li>
					<li><code>month</code> - every month of using the job board costs as much as <strong><code>budget-amount</code></strong> indicates.</li>
					<li><code>year</code> - every year of using the job board costs as much as <strong><code>budget-amount</code></strong> indicates.</li>
				</ul>
			</li>
			<li><strong><code>budget-amount</code></strong> - optional; if, for the particular portal, there exists an Extra Field with different types of credits, the cost can be set for each <code>option</code>:
				<ul>
					<li><code>label</code> - name of the credit type - obtainable via <a href="https://github.com/oneworldmarket/idibu-api/blob/master/webservices/quota-management/quota-settings-for-specified-portal.md" target="_blank">quota-settings-for-specified-portal.</a></li>
					<li><code>value</code> - the actual cost for this credit type.</li>
				</ul>
			</li>
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
	&lt;period&gt;Month&lt;/period&gt;
	&lt;base&gt;Post&lt;/base&gt;
	&lt;month-renewal&gt;05&lt;/month-renewal&gt;
	&lt;year-renewal/&gt;
	&lt;reset&gt;Carry&lt;/reset&gt;
	&lt;budget-type&gt;payperpost&lt;/budget-type&gt;
	&lt;budget-amount&gt;
		&lt;option&gt;
			&lt;label&gt;Standard job&lt;/label&gt;
			&lt;value&gt;2700&lt;/value&gt;
		&lt;/option&gt;
		&lt;option&gt;
			&lt;label&gt;Premium job&lt;/label&gt;
			&lt;value&gt;13&lt;/value&gt;
		&lt;/option&gt;
		&lt;option&gt;
			&lt;label&gt;Default ad&lt;/label&gt;
			&lt;value&gt;2.20&lt;/value&gt;
		&lt;/option&gt;
	&lt;/budget-amount&gt;
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
