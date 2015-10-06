<p>Method to list custom currencies for specific clients based on the hash id</p>
<h1>
	list of currencies idibu can support</h1>
<pre>
<code>http://ws.idibu.com/ws/rest/v1/currencies?hash=<hash></code></pre>
<pre>
<code type="xml">
&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
&lt;response&gt;
    &lt;currencies&gt;
        &lt;currency&gt;
            &lt;id&gt;AED&lt;/id&gt;
            &lt;name&gt;UAE Dirham &lt;/name&gt;
        &lt;/currency&gt;
            (...)
    &lt;/currencies&gt;
&lt;/response&gt;
&lt;/idibu&gt;</code>
</pre>
<pre>
<code>http://ws.idibu.com/ws/rest/v1/currencies/available?hash=<hash></code></pre>

<div id="ember3852" class="ember-view js-task-list-container">  <p>You can also set anyavailable currencies:</p>

<pre><code>POST ws/rest/v1/currencies/available
</code></pre>

<div class="highlight highlight-text-xml"><pre>&lt;<span class="pl-ent">idibu</span>&gt;
    &lt;<span class="pl-ent">currencies</span>&gt;
        &lt;<span class="pl-ent">currency</span>&gt;USD&lt;/<span class="pl-ent">currency</span>&gt;
        &lt;<span class="pl-ent">currency</span>&gt;ZWD&lt;/<span class="pl-ent">currency</span>&gt;
    &lt;/<span class="pl-ent">currencies</span>&gt;
&lt;/<span class="pl-ent">idibu</span>&gt;</pre></div>

<p>And revert to default:</p>

<pre><code>DELETE ws/rest/v1/currencies/available
</code></pre>
  <textarea id="ember3853" class="js-task-list-field ember-view ember-text-area"></textarea>
</div>
