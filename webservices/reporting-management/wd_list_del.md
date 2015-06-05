This service allows you to view client's reporting watchdogs.
<pre>
<code>
GET: ws.idibu.com/ws/rest/v1/report-watchdogs/?hash=CLIENTS_HASH
</code></pre>
<h2>
	Response</h2>
<pre>
<code type="xml">
&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
  &lt;response&gt;
    &lt;watchdogs&gt;
      &lt;watchdog&gt;
        &lt;id&gt;5059&lt;/id&gt;
        &lt;name&gt;WD test&lt;/name&gt;
        &lt;type&gt;status&lt;/type&gt;
        &lt;frequency&gt;monthly&lt;/frequency&gt;
        &lt;range&gt;month&lt;/range&gt;
        &lt;email&gt;bart@idibu.com&lt;/email&gt;
        &lt;details&gt;
          &lt;offices&gt;
            &lt;office&gt;35000027&lt;/office&gt;
          &lt;/offices&gt;
          &lt;teams&gt;&lt;/teams&gt;
          &lt;profiles&gt;&lt;/profiles&gt;
          &lt;include-inactive&gt;no&lt;/include-inactive&gt;
          &lt;boards&gt;&lt;/boards&gt;
        &lt;/details&gt;
        &lt;created&gt;2015-06-03 15:43:42&lt;/created&gt;
      &lt;/watchdog&gt;
    &lt;/watchdogs&gt;
  &lt;/response&gt;
  &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>

You can also deleted chosen reporting watchdog:

<pre>
<code>
DELETE: ws.idibu.com/ws/rest/v1/report-watchdogs/WATCHDOG_ID?hash=CLIENTS_HASH
</code></pre>
