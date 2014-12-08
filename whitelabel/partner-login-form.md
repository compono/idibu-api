<p>If you are setting up a whitelabel version of idibu and want to place the login form within your own website or system, the following is an example of the minimum code required to do this:</p>
<pre>
<code>
&lt;form id=&quot;idibu_login&quot; action=&quot;&quot; method=&quot;post&quot;&gt;
    &lt;p&gt;
        &lt;label for=&quot;idibu_username&quot;&gt;Username&lt;/label&gt;&lt;br /&gt;
        &lt;input type=&quot;text&quot; id=&quot;idibu_username&quot;&gt;
    &lt;/p&gt;
    &lt;p&gt;
        &lt;label for=&quot;idibu_password&quot;&gt;Password&lt;/label&gt;&lt;br /&gt;
        &lt;input type=&quot;password&quot; id=&quot;idibu_password&quot;&gt;
    &lt;/p&gt;
    &lt;p&gt;
        &lt;button id=&quot;idibu_submit&quot;&gt;Login&lt;/button&gt;
    &lt;/p&gt;
&lt;/form&gt;
<script type="text/javascript" src="http://www.idibu.com/clients/libs/js/idibu-whitelabel.js"></script>
</code></pre>
