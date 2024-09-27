<p>Method returns quota settings for specified portal. Refer to <a href="https://github.com/oneworldmarket/idibu-api/blob/master/webservices/quota-management/add-quota-to-portal.md" target="_blank">add-quota-to-portal</a> to understand the parameters.</p>
<h1>Parameters</h1>
<p>No additional parameters</p>
<h1>Example</h1>
<h2>Request</h2>
<pre><code>https://ws.idibu.com/ws/rest/v1/quotas/517?hash=YOUR_HASH</code></pre>
<h2>Response</h2>
<pre><code type="xml">&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
	&lt;response&gt;
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
			&lt;/option&gt;
				&lt;label>Featured job</label>
				&lt;value/>
			&lt;/option&gt;
			&lt;option>
				&lt;label>Premium+ job</label>
				&lt;value/>
			&lt;/option&gt;
			&lt;option&gt;
				&lt;label>IT job</label>
				&lt;value/>
			&lt;/option&gt;
			&lt;option&gt;
				&lt;label>Free job</label>
				&lt;value/>
			&lt;/option>
		&lt;/budget-amount&gt;
	&lt;/response&gt;
	&lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
