<p>The post completion page simplifies multi-posting so that a user, after sending core job data to the system, can complete additional field information, choose additional boards to post to, set durations etc - all from one page with no multi-step process.</p>
<p>It means this page can be brought back and embeed inside the third-party system allowing much tighter system integration and user workflow.</p>
<h1>
	Posting Completion Page (PCP) configuration Tags</h1>
<p>To control how the PCP works, there is a complete set of tags. Right below is the list of tags and what they are for, and we have <a href="/docs/xml-api-v3-examples">several examples</a> of their usage.</p>
<h2>
	idibu returns a PCP, or you force it</h2>
<p>If our system founds what is considered a non critical error (i.e., there&#39;s a missing required field for one of the boards, or no suitable boards are found - either the provided board ids are incorrect or no board tag was provided directly) or the configuration tags forces the system to return a PCP - more on this later - the message returned by idibu will contain a url pointing to a PCP, that contains the data from the account (i.e., the boards the client is subscribed to) for the board extracted from the request (i.e., the extra fields).</p>
<p>If we find a non critical error, idibu will return a PCP. The full set of reasons for returning a PCP are:</p>
<ul>
	<li>
		Non critical errors
		<ul>
			<li>
				At least one required extra field is missing (or contains wrong data)</li>
			<li>
				The board ids provided are wrong, or the account is not subscribed to any of them, resulting in idibu finding zero valid board ids</li>
			<li>
				The board duration for at least one of the boards is wrong</li>
			<li>
				There is no board tags whatsoever</li>
		</ul>
	</li>
	<li>
		PCP forcing configuration tag values
		<ul>
			<li>
				The request indicates that the boards are not &#39;locked&#39; so the consultant can add boards to post to</li>
			<li>
				Some of the core fields are marked as editable - more on this later</li>
		</ul>
	</li>
</ul>
