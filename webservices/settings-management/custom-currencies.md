<p>Method to list custom currencies for specific clients based on the hash id</p>
<h2>List of all currencies idibu can support</h2>
<h3>Request</h3>
<pre>
<code>https://ws.idibu.com/ws/rest/v1/currencies?hash=<hash></code></pre>
<h2>Obtaining available currencies for a particular account</h2>
<h3>Request</h3>
<pre>
<code>https://ws.idibu.com/ws/rest/v1/currencies/available?hash=<hash></code></pre>
<h2>Setting available currencies for a particular account</h2>
<h3>Request</h3>
<pre><code>POST https://ws.idibu.com/ws/rest/v1/currencies/available?hash=<hash></code>
&lt;<span class="pl-ent">idibu</span>&gt;
    &lt;<span class="pl-ent">currencies</span>&gt;
        &lt;<span class="pl-ent">currency</span>&gt;USD&lt;/<span class="pl-ent">currency</span>&gt;
        &lt;<span class="pl-ent">currency</span>&gt;ZWD&lt;/<span class="pl-ent">currency</span>&gt;
    &lt;/<span class="pl-ent">currencies</span>&gt;
&lt;/<span class="pl-ent">idibu</span>&gt;</pre></div></pre>
<h2>Reverting to default for a particular account</h2>
<h3>Request</h3>
<pre><code>DELETE https://ws.idibu.com/ws/rest/v1/currencies/available?hash=<hash></code></pre>
</div>
