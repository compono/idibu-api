<p>The method allows to view or set the display of non-required (only!) extra fields on the portal:</p>
<ul>
  <li><strong><code>default</code></strong> - by default all non-required extra fields are setup this way. Such fields will be non-required when posting.</li>
  <li><strong><code>required</code></strong> - makes the field mandatory when posting.</li>
  <li><strong><code>hide</code></strong> - hides the field and ignores it when posting.</li>
</ul>
<h1>Parameters</h1>
<p>No additional parameters.</p>
<h1>Example - obtaining current setup</h1>
<p>To view the current settings, just fire a GET request to the webservice.</p>
<h2>Request</h2>
<pre><code>GET https://ws.idibu.com/ws/rest/v1/portals/517/extra-fields-display?hash=YOUR_HASH</code></pre>
<h2>Response</h2>
<pre><code type="xml">&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
	&lt;response&gt;
		&lt;fields&gt;
			&lt;field&gt;
				&lt;name&gt;uaptemplate_517&lt;/name&gt;
				&lt;display&gt;default&lt;/display&gt;
			&lt;/field&gt;
			&lt;field&gt;
				&lt;name&gt;idibu_salary&lt;/name&gt;
				&lt;display&gt;required&lt;/display&gt;
			&lt;/field&gt;
		&lt;/fields&gt;
	&lt;/response&gt;
	&lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
<h1>Example - editing the fields</h1>
<p>To edit or set the options, fire a POST request with an appropriate XML (see below) inside the <code>data</code> parameter.</p>
<h2>Request</h2>
<pre><code>POST https://ws.idibu.com/ws/rest/v1/portals/517/extra-fields-display?hash=YOUR_HASH</code></pre>
<pre><code type="xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
	&lt;response&gt;
		&lt;fields&gt;
			&lt;field&gt;
				&lt;name&gt;uaptemplate_517&lt;/name&gt;
				&lt;display&gt;hide&lt;/display&gt;
			&lt;/field&gt;
			&lt;field&gt;
				&lt;name&gt;idibu_salary&lt;/name&gt;
				&lt;display&gt;required&lt;/display&gt;
			&lt;/field&gt;
		&lt;/fields&gt;
	&lt;/response&gt;
	&lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
<h2>Response</h2>
<pre><code type="xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
	&lt;response&gt;
		&lt;message&gt;Updated display settings&lt;/message&gt;
	&lt;/response&gt;
	&lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
