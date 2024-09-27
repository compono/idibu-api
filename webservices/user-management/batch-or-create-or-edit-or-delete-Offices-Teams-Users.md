Method that allows you to bulk add, delete, edit offices, teams and users all in a single call
<h1>
	Parameters</h1>
<p>No additional parameters</p>
<h1>
	Example</h1>
<h2>
	Data posted</h2>
<pre>
<code>
https://ws.idibu.com/ws/rest/v1/offices-teams-users?hash=<your hash>
</code></pre>
<pre>
<code type="xml">
&lt;idibu&gt;
  &lt;user&gt;&lt;!-- creates new user, format identical to users/new ws --&gt;
    &lt;profile&gt;
      &lt;team-id&gt;42&lt;/team-id&gt;&lt;!-- required --&gt;
    &lt;/profile&gt;
  &lt;/user&gt;
  &lt;user id=&quot;13&quot;&gt;&lt;!-- updates user data --&gt;
  &lt;/user&gt;
  &lt;user delete=&quot;true&quot; id=&quot;14&quot;&gt;&lt;!-- deletes user and his login, if exists --&gt;

  &lt;team&gt;&lt;!-- creates new team, format identical to teams/new ws --&gt;
     &lt;name&gt;Test Team&lt;/name&gt;&lt;!-- required --&gt;
     &lt;office-id&gt;7&lt;/office-id&gt;&lt;!-- required --&gt;
  &lt;/team&gt;
  &lt;team id=&quot;1&quot;&gt;&lt;!-- updates team data --&gt;
  &lt;/team&gt;
  &lt;team delete=&quot;true&quot; id=&quot;2&quot;&gt;&lt;!-- deletes team, and moves its users to unassigned --&gt;

  &lt;office&gt;&lt;!-- creates new office, format identical to offices/new ws --&gt;
     &lt;name&gt;Test Office&lt;/name&gt;&lt;!-- required --&gt;
  &lt;/office&gt;
  &lt;office id=&quot;7&quot;&gt;&lt;!-- updates office data --&gt;
  &lt;/office&gt;
  &lt;office delete=&quot;true&quot; id=&quot;8&quot;&gt;&lt;!-- deletes office and it&#39;s teams --&gt;
&lt;/office&gt;&lt;/team&gt;&lt;/user&gt;&lt;/idibu&gt;
</code></pre>
