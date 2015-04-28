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
<p>You have to change the boardID parameter to match the board you want to fetch data for, the list of valid ids is fetched from the previous list. ProfileID will be significant for selected boards (i.e. Linkedin) where the extrafields differ based on user&#39;s logins.<br><br>
The list of data returned by this XML contains:<ul>
<li>Board information - name, description, logo link, posting information</li>
<li>Field validation restrains</li>
<li>List of available extra fields with their values and attributes</li>
<li>Board duration options</li>
</ul>
<h1>
List of possible field validators</h1>
<ul>
Field Length validators
<li>fieldMaxLength - Maximum Field Length.</li>
<li>fieldMinLength - Minimum Field Length.</li>
<li>fieldMaxWords - Maximum Field Words Count.</li>
<li>fieldMinWords - Minimum Field Words Count.</li>
<li>fieldLengthIs - Exact Field Length.</li>
<li>listHasMinChoices - Minimum choice count (for multiselect fields).</li>
<li>listHasMaxChoices - Maximum choice count (for multiselect fields).</li>
<li>fieldWithoutLinks - Can't contain links.</li>
<li>fieldWithoutEmails - Can't contain emails.</li>
<br>
Numberic Validators<br>
<li>intMaxSize - Integer Value Less Than.</li>
<li>intMinSize - Integer Value Greater Than.</li>
<br>Data Type Validators<br>
<li>onlyNumbers - Only Allow Numbers.</li>
<li>fieldHasProperLink - Only allow urls.</li>
<li>validUKPostCode - Checking if the provided field is filled with valid UK post code. Only applies to vacancies being posted to UK.</li>
</ul>

<h1>
Extra field attributes</h1>
<ul>
Field Length validators
<li>name - Field name as it should be passed to idibu.</li>
<li>description - Field name as it should be displayed to a user.</li>
<li>type - Text/select/hidden.</li>
<li>multi - If true, possible to select multiple values.</li>
<li>validated - If true, has a validator that is assigned to this field and present in the same XML.</li>
<li>required - If true, has be provided in the XML in order to complete the posting. Without it idibu will ask to complete the PCP link.</li>
<li>order - Figure that symbolises the order of the field between other extra fields (as it is in idibu).</li>
</ul>

<h1>
Board data example XML</h1>
<pre>
<code type="xml">
&lt;?xml version=&quot;1.0&quot; encoding=&quot;ISO-8859-1&quot; ?&gt;
&lt;idibu&gt;
&lt;boards&gt;
	&lt;board id=&quot;517&quot; last_modified=&quot;2010-01-14 00:00:00&quot; published=&quot;true&quot; supports_delete=&#39;Yes&#39;&gt;
	&lt;name&gt;&lt;![CDATA[idibu Developer Board]]&gt;&lt;/name&gt;
	&lt;description&gt;
	&lt;![CDATA[
	&lt;p&gt;Hello! This a job board purely for development purposes. It requires no login details and is designed to allow external developers to use the posting facility without sending test data to real job boards. You can view data posted at http://jobboardtest.idibu.com.&lt;/p&gt;
	]]&gt;
	&lt;/description&gt;
	&lt;tags&gt;
		&lt;tag&gt;517&lt;/tag&gt;
	&lt;/tags&gt;
	&lt;validators&gt;
		&lt;rule type=&quot;fieldMaxLength&quot; control=&quot;6000&quot;&gt;
			&lt;field&gt;description&lt;/field&gt;
			&lt;message&gt;&lt;![CDATA[idibu dev board accepts 6000 characters for description.]]&gt;&lt;/message&gt;
		&lt;/rule&gt;
		&lt;rule type=&quot;fieldWithoutLinks&quot;&gt;
			&lt;field&gt;description&lt;/field&gt;
			&lt;message&gt;&lt;![CDATA[idibu developer board does not accept links]]&gt;&lt;/message&gt;
		&lt;/rule&gt;
	&lt;/validators&gt;
	&lt;durations&gt;
		&lt;duration value=&quot;7&quot;&gt;1 week&lt;/duration&gt;
		&lt;duration value=&quot;14&quot;&gt;2 weeks&lt;/duration&gt;
		&lt;duration value=&quot;21&quot;&gt;3 weeks&lt;/duration&gt;
		&lt;duration value=&quot;28&quot;&gt;4 weeks&lt;/duration&gt;
		&lt;duration value=&quot;365&quot;&gt;a year&lt;/duration&gt;
	&lt;/durations&gt;
	&lt;extrafields&gt;
		&lt;extrafield name=&quot;devboard_url&quot;  dynfield=&quot;app_url&quot; description=&quot;Application URL&quot; type=&quot;hidden&quot; /&gt;
		&lt;extrafield name=&quot;uaptemplate_517&quot;  description=&quot;Template&quot; type=&quot;select&quot;&gt;
			&lt;data&gt;
				&lt;option&gt;Default&lt;/option&gt;
			&lt;/data&gt;
		&lt;/extrafield&gt;
		&lt;extrafield name=&quot;idibudts_cat&quot;  description=&quot;Job Sector&quot; type=&quot;select&quot; order=&quot;20&quot; required=&quot;true&quot;&gt;
			&lt;data&gt;
				&lt;option&gt;Please Select...&lt;/option&gt;
				&lt;option id=&quot;3&quot;&gt;Administrators&lt;/option&gt;
				&lt;option id=&quot;6&quot;&gt;Editors&lt;/option&gt;
				&lt;option id=&quot;7&quot;&gt;Marketers&lt;/option&gt;
				&lt;option id=&quot;2&quot;&gt;Designers&lt;/option&gt;
				&lt;option id=&quot;8&quot;&gt;Managers&lt;/option&gt;
				&lt;option id=&quot;5&quot;&gt;Testers&lt;/option&gt;
				&lt;option id=&quot;9&quot;&gt;Consultants&lt;/option&gt;
				&lt;option id=&quot;1&quot;&gt;Programmers&lt;/option&gt;
				&lt;option id=&quot;NEW&quot;&gt;Hello&lt;/option&gt;
			&lt;/data&gt;
		&lt;/extrafield&gt;
		&lt;extrafield name=&quot;idibu_salary&quot;  dynfield=&quot;salaryOverride&quot; description=&quot;DevBoard salary override&quot; type=&quot;hidden&quot; order=&quot;30&quot; /&gt;
		&lt;extrafield name=&quot;dev_url&quot;  dynfield=&quot;app_url&quot; description=&quot;Application URL&quot; type=&quot;text&quot; order=&quot;40&quot; /&gt;
	&lt;/extrafields&gt;
	&lt;dynfields&gt;
		&lt;dynfield name=&quot;app_url&quot; type=&quot;text&quot; description=&quot;Application URL (Optional)&quot; /&gt;
		&lt;dynfield name=&quot;salaryOverride&quot; type=&quot;text&quot; description=&quot;Salary Text Override (Optional)&quot; /&gt;
	&lt;/dynfields&gt;
	&lt;/board&gt;
&lt;/boards&gt;
&lt;/idibu&gt;
</code></pre>
</p>
