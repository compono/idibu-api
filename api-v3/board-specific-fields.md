<p>When using the XML API you may need to be sending job board extra field data depending on how you plan to integrate. These two services provide a listing of job boards your account is subscribed to as well as individual board listings showing extra field items and their values.</p>
<h1>
	List of Job Boards</h1>
<pre>
<code>http://ws.idibu.com/clients/json.php?class=Portal&action=UserPortal&format=XML&list=subscribed&hash=[INSERT LOGIN HASH HERE]</code></pre>
<p>The valid values for the list parameter are: all, subscribed, unsubscribed.</p>
<p>The properties of the board tag are:</p>
<ul>
	<li>
		id - board id</li>
	<li>
		published &ndash; should be set to &#39;true&#39; if the board is active</li>
	<li>
		allows_html &ndash; if set you can use html in the description</li>
	<li>
		last_modified &ndash; date the board was last updated</li>
	<li>
		subscribed &ndash; a user should only post to the boards they are subscribed to</li>
</ul>
<h1>
	Get Board Data</h1>
<pre>
<code>http://ws.idibu.com/clients/json.php?class=Portal&action=showData&boardID=10&format=XML&hash=[INSERT LOGIN HASH HERE]&profileID=[SENDER ID HERE]</code></pre>
<p>You have to change the boardID parameter to match the board you want to fetch data for, the list of valid ids is fetched from the previous list. ProfileID will be significant for selected boards (i.e. Linkedin) where the extrafields differ based on user&#39;s logins.</p>
