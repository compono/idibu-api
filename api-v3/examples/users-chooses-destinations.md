<p>If the selection of posting destinations is left completely to the discretion of the user, the request can be sent with an empty post block:</p>
<pre>
<code>
&lt;!-- ... --&gt;
&nbsp;&nbsp;&lt;location id=&quot;GB&quot;&gt;&lt;/location&gt;
&nbsp;&nbsp;&lt;sublocation id=&quot;1024195&quot;&gt;&lt;/sublocation&gt;
&nbsp;&nbsp;&lt;posts&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;!-- Look mom, no boards! --&gt;
&nbsp;&nbsp;&lt;/posts&gt;
&nbsp;&lt;/job&gt;
&lt;/idibu&gt;
</code></pre>
<p>These type of requests will return a PCP as well.</p>
<p><strong>If no posting destination data is sent in the request, the value of the lockboards config tag has to be &quot;Yes&quot;. </strong></p>
<p>Sending an empty posting destination block with a value of &quot;No&quot; in lockboards will result in a critical error, as the configuration is given precedence over the post data.</p>
<p>&nbsp;</p>
