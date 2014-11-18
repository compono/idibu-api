<p>Method gets or sets aptrack settings for an account</p>
<h1>
	Parameters</h1>
<p>No additional parameters for this request</p>
<h1>
	Example of getting settings</h1>
<h2>
	Request</h2>
<pre>
<code>
http://ws.idibu.com/ws/rest/v1/settings/aptrack?hash=<your hash>
</code></pre>
<h2>
	Response</h2>
<pre>
<code type="xml">
&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
  &lt;response&gt;
    &lt;users-can-see-aptrack&gt;yes&lt;/users-can-see-aptrack&gt;
    &lt;statuses&gt;
      &lt;status&gt;
        &lt;extra-id&gt;&lt;/extra-id&gt;
        &lt;order&gt;&lt;/order&gt;
        &lt;name&gt;Rejected&lt;/name&gt;
        &lt;label&gt;Declined&lt;/label&gt;
        &lt;enabled&gt;no&lt;/enabled&gt;
        &lt;group&gt;general&lt;/group&gt;
        &lt;forward-cv&gt;no&lt;/forward-cv&gt;
        &lt;has-responder&gt;no&lt;/has-responder&gt;
        &lt;responder&gt;
          &lt;subject&gt;&lt;/subject&gt;
        &lt;/responder&gt;
      &lt;/status&gt;
      &lt;status&gt;
        &lt;label&gt;Declined&lt;/label&gt;
      &lt;/status&gt;
      &lt;status&gt;
        &lt;extra-id&gt;15&lt;/extra-id&gt;
        &lt;order&gt;1&lt;/order&gt;
        &lt;name&gt;Keep on File&lt;/name&gt;
        &lt;label&gt;Keep on File&lt;/label&gt;
        &lt;enabled&gt;yes&lt;/enabled&gt;
        &lt;group&gt;star&lt;/group&gt;
        &lt;forward-cv&gt;yes&lt;/forward-cv&gt;
        &lt;has-responder&gt;no&lt;/has-responder&gt;
        &lt;responder&gt;
          &lt;subject&gt;&lt;/subject&gt;
        &lt;/responder&gt;
      &lt;/status&gt;
      &lt;status&gt;
        &lt;extra-id&gt;14&lt;/extra-id&gt;
        &lt;order&gt;1&lt;/order&gt;
        &lt;name&gt;Invite in for Interview&lt;/name&gt;
        &lt;label&gt;Invite in for Interview&lt;/label&gt;
        &lt;enabled&gt;yes&lt;/enabled&gt;
        &lt;group&gt;green&lt;/group&gt;
        &lt;forward-cv&gt;yes&lt;/forward-cv&gt;
        &lt;has-responder&gt;yes&lt;/has-responder&gt;
        &lt;responder&gt;
          &lt;subject&gt;Please come in for an interview&lt;/subject&gt;&amp;lt;p&amp;gt;Some stuff here&amp;amp;nbsp;[JOB_TITLE]&amp;lt;/p&amp;gt;
        &lt;/responder&gt;
      &lt;/status&gt;
      &lt;status&gt;
        &lt;extra-id&gt;16&lt;/extra-id&gt;
        &lt;order&gt;1&lt;/order&gt;
        &lt;name&gt;test&lt;/name&gt;
        &lt;label&gt;test&lt;/label&gt;
        &lt;enabled&gt;no&lt;/enabled&gt;
        &lt;group&gt;green&lt;/group&gt;
        &lt;forward-cv&gt;yes&lt;/forward-cv&gt;
        &lt;has-responder&gt;no&lt;/has-responder&gt;
        &lt;responder&gt;
          &lt;subject&gt;&lt;/subject&gt;
        &lt;/responder&gt;
      &lt;/status&gt;
      &lt;status&gt;
        &lt;extra-id&gt;17&lt;/extra-id&gt;
        &lt;order&gt;1&lt;/order&gt;
        &lt;name&gt;changed status :)&lt;/name&gt;
        &lt;label&gt;changed status :)&lt;/label&gt;
        &lt;enabled&gt;no&lt;/enabled&gt;
        &lt;group&gt;green&lt;/group&gt;
        &lt;forward-cv&gt;no&lt;/forward-cv&gt;
        &lt;has-responder&gt;no&lt;/has-responder&gt;
        &lt;responder&gt;
          &lt;subject&gt;&lt;/subject&gt;
        &lt;/responder&gt;
      &lt;/status&gt;
    &lt;/statuses&gt;
    &lt;disable-duplicate&gt;no&lt;/disable-duplicate&gt;
    &lt;auto-responders&gt;
      &lt;receive&gt;
        &lt;subject&gt;test&lt;/subject&gt;[APPLICANT_NAME]
      &lt;/receive&gt;
      &lt;reject&gt;
        &lt;subject&gt;Sorry, you were rejected&lt;/subject&gt;test2
      &lt;/reject&gt;
    &lt;/auto-responders&gt;
    &lt;forward&gt;
      &lt;immediately&gt;teams&lt;/immediately&gt;
      &lt;held-in-aptrack-forward-to&gt;sender&lt;/held-in-aptrack-forward-to&gt;
      &lt;teams&gt;
    &lt;/teams&gt;&lt;/forward&gt;
    &lt;block-extensions&gt;gif,png,jpg,jpeg,tif,tiff,exe,pdf&lt;/block-extensions&gt;
  &lt;/response&gt;
  &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
<h1>
	Example of setting settings</h1>
<p><b>Please note</b>, that for base system statuses (where extra-id is not set, usualy only Rejected) in order to change them you have to provide status name, for extended (custom) statuses in order to change them you have to provide extra-id. Also, for base statuses you can change only label and disable it or enable. For extended statuses by changing their label you&#39;re also changing status name. Value of tag &#39;group&#39; can be one of these values: &#39;green&#39;, &#39;yellow&#39;, &#39;red&#39;, &#39;orange&#39;, &#39;blue&#39;, &#39;star&#39;. To create a new custom status just set extra-id to 0 and fill needed fields.</p>
<p>For forwarding rules value of tag &#39;immediately&#39; can be one of these values: &#39;yes&#39;, &#39;no&#39;, &#39;teams&#39;.</p>
<h2>
	Request</h2>
<pre>
<code>
POST http://ws.idibu.com/ws/rest/v1/settings/system?hash=<your hash>
</code>
<code type="xml">
&lt;?xml version=&quot;1.0&quot;?&gt;
&lt;idibu&gt;
  &lt;users-can-see-aptrack&gt;yes&lt;/users-can-see-aptrack&gt;
  &lt;disable-duplicate&gt;no&lt;/disable-duplicate&gt;
  &lt;block-extensions&gt;gif,png,tif,tiff,jpg,exe,pdf&lt;/block-extensions&gt;
  &lt;forward&gt;
    &lt;immediately&gt;teams&lt;/immediately&gt;
    &lt;held-in-aptrack-forward-to&gt;sender&lt;/held-in-aptrack-forward-to&gt;
    &lt;teams&gt;&lt;/teams&gt;
  &lt;/forward&gt;
  &lt;auto-responders&gt;
    &lt;receive&gt;
      &lt;subject&gt;test&lt;/subject&gt;[APPLICANT_NAME]
    &lt;/receive&gt;
    &lt;reject&gt;test2
    &lt;/reject&gt;
  &lt;/auto-responders&gt;
  &lt;statuses&gt;
    &lt;status&gt;
      &lt;extra-id&gt;17&lt;/extra-id&gt;
      &lt;name&gt;changed status :)&lt;/name&gt;
    &lt;/status&gt;
    &lt;status&gt;
      &lt;name&gt;Rejected&lt;/name&gt;
      &lt;label&gt;Declined&lt;/label&gt;
      &lt;enabled&gt;no&lt;/enabled&gt;
    &lt;/status&gt;
  &lt;/statuses&gt;
&lt;/idibu&gt;
&lt;/code&gt;
&lt;/pre&gt;
&lt;h2&gt;
	Response&lt;/h2&gt;
&lt;pre&gt;
&lt;code type=&quot;xml&quot;&gt;
&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
  &lt;response&gt;
    &lt;message&gt;Settings updated&lt;/message&gt;
  &lt;/response&gt;
  &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code>
</pre>
