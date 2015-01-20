<p>This service allows you to quickly check which boards can a user post to and whether user has logins/quota necessary. This can be used to prepare a list of boards user can post to in partner system.<br>
The force posting tag represents the state of the board that admin chose for the selected user. It can be:<br>
<br>
no - board should not be preselected and selectable<br>
select - board should be preselected with an un-select option<br>
force - board should be preselected with no un-select option<br>
<br>
We request that you incorporate those options into your integration if you are using this webservice.
</p>
<h1>
	Example</h1>
<h2>
	Posted data</h2>
<pre>
<code>
http://ws.idibu.com/ws/rest/v1/users/[user id]/portals-available?hash=<your hash>
</code></pre>
<h2>
	Response</h2>
<pre>
<code type="xml">
&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
&lt;response&gt;
	&lt;portals&gt;
		&lt;portal id=&quot;1504&quot;&gt;
			&lt;name&gt;Facebook&lt;/name&gt;
			&lt;quota&gt;&lt;/quota&gt;
			&lt;remaining_quota&gt;
			&lt;/remaining_quota&gt;
			&lt;has_logins&gt;yes&lt;/has_logins&gt;
			&lt;force_posting&gt;select&lt;/force_posting&gt;
		&lt;/portal&gt;
		&lt;portal id=&quot;517&quot;&gt;
			&lt;name&gt;idibu Developer Board&lt;/name&gt;
			&lt;quota&gt;0&lt;/quota&gt;
			&lt;remaining_quota&gt;0&lt;/remaining_quota&gt;
			&lt;has_logins&gt;yes&lt;/has_logins&gt;
			&lt;force_posting&gt;no&lt;/force_posting&gt;
		&lt;/portal&gt;
	&lt;/portals&gt;
&lt;/response&gt;
&lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;

</code></pre>
