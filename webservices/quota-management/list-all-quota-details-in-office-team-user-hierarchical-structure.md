<p>This method displays office/team/user quotas in hierarchy for optimal read and display speed.<br/>
	<code>quota</code> is the amount of quotas.<br/>
	<code>limit</code> is the amount to which the quotas reset after the specified period (see <a href="https://github.com/oneworldmarket/idibu-api/blob/master/webservices/quota-management/add-quota-to-portal.md" target="_blank">add-quota-to-portal<a/>).<br/>
	<code>remaining</code> is the amount of quota currently remaining.</p>
<p>You can use an additional <code>hideEmpty=true</code> parameter in the request - the response will then not display any users, teams or offices that have no quotas setup.</p>
<h3>Request</h3>
<pre><code>http://www.idibu.com/ws/rest/v1/quotas/(board id)/all?hash=YOUR_HASH</code></pre>
<h3>Response</h3>
<pre>
<code type="xml">&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
	&lt;response&gt;
		&lt;offices&gt;
			&lt;office&gt;
				&lt;team-id&gt;35000000&lt;/team-id&gt;
				&lt;quota&gt;808&lt;/quota&gt;
				&lt;limit&gt;808&lt;/limit&gt;
				&lt;remaining&gt;808&lt;/remaining&gt;
				&lt;name&gt;Example office&lt;/name&gt;
				&lt;teams&gt;
					&lt;team&gt;
						&lt;team-id&gt;35000001&lt;/team-id&gt;
						&lt;quota&gt;5&lt;/quota&gt;
						&lt;limit&gt;5&lt;/limit&gt;
						&lt;remaining&gt;5&lt;/remaining&gt;
						&lt;name&gt;Example team&lt;/name&gt;
						&lt;users&gt;
							&lt;user&gt;
								&lt;user-id&gt;3&lt;/user-id&gt;
								&lt;quota&gt;200&lt;/quota&gt;
								&lt;limit/&gt;
								&lt;remaining&gt;200&lt;/remaining&gt;
								&lt;name&gt;Example user1&lt;/name&gt;
							&lt;/user&gt;
							&lt;user&gt;
								&lt;user-id&gt;80&lt;/user-id&gt;
								&lt;quota/&gt;
								&lt;limit/&gt;
								&lt;remaining/&gt;
								&lt;name&gt;Example user2&lt;/name&gt;
							&lt;/user&gt;
						&lt;/users&gt;
					&lt;/team&gt;
				&lt;/teams&gt;
			&lt;/office&gt;
		&lt;/offices&gt;
		&lt;unassigned&gt;
			&lt;users&gt;
				&lt;user&gt;
					&lt;user-id&gt;25&lt;/user-id&gt;
					&lt;quota/&gt;
					&lt;limit/&gt;
					&lt;remaining/&gt;
					&lt;name&gt;no team/office user1&lt;/name&gt;
				&lt;/user&gt;
				&lt;user&gt;
					&lt;user-id&gt;153&lt;/user-id&gt;
					&lt;quota&gt;12&lt;/quota&gt;
					&lt;limit/&gt;
					&lt;remaining&gt;12&lt;/remaining&gt;
					&lt;name&gt;no team/office user2&lt;/name&gt;
				&lt;/user&gt;
			&lt;/users&gt;
		&lt;/unassigned&gt;
	&lt;/response&gt;
	&lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
