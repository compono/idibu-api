<p><b>Although there are some examples in the API documentation page, this page has a comprehensive set of examples regarding the use of the API.</b></p>
<p>We tried to make the examples as easy as possible to understand, but if there isn&#39;t clear enough, please check the stated documentation page for an in depth explanation. If things are still unclear, please use the <a href="/forum">support forum</a> to get answers to your questions.</p>
<p><em><strong>This section uses this standard this XML payload as a reference for all the examples:</strong></em></p>
<pre>
<code>
&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot; ?&gt;
&lt;idibu&gt;
&nbsp;&nbsp;&lt;method&gt;ADD&lt;/method&gt;
&nbsp;&nbsp;&lt;config&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;show_durations&gt;No&lt;/show_durations&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;lockboards&gt;Yes&lt;/lockboards&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;partnerid&gt;yourpartnerid&lt;/partnerid&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;redirecturl&gt;http://www.google.com&lt;/redirecturl&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;validate_level&gt;Warning&lt;/validate_level&gt;
&nbsp;&nbsp;&lt;/config&gt;
&nbsp;&nbsp;&lt;job&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;sender id=&quot;31000383&quot;&gt;&lt;/sender&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;title&gt;&lt;![CDATA[Here goes the job title]]&gt;&lt;/title&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;description&gt;&lt;![CDATA[This is a job description can be long]]&gt;&lt;/description&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;reference&gt;2080&lt;/reference&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;startdate&gt;2011-07-07&lt;/startdate&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;duration&gt;5 years&lt;/duration&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;salarymin&gt;30000&lt;/salarymin&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;salarymax&gt;40000&lt;/salarymax&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;salaryper value=&quot;annum&quot;&gt;&lt;/salaryper&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;salaryextras&gt;lots&lt;/salaryextras&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;salaryOverride&gt;Salary override text&lt;/salaryOverride&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;currency&gt;EU&lt;/currency&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;jobtype id=&quot;2&quot;&gt;&lt;/jobtype&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;job_time&gt;2&lt;/job_time&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;category id=&quot;1&quot;&gt;&lt;/category&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;location id=&quot;GB&quot;&gt;&lt;/location&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;sublocation id=&quot;1024195&quot;&gt;&lt;/sublocation&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;posts&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;board id=&quot;517&quot;&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;duration days=&quot;2&quot;&gt;&lt;/duration&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;extrafield name=&quot;idibudts_cat&quot;&gt;1&lt;/extrafield&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;extrafield name=&quot;app_url_test&quot;&gt;http://somesite.com/example_app_url.htm&lt;/extrafield&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;extrafield name=&quot;idibu_pcode&quot;&gt;EC1A&lt;/extrafield&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/board&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;board id=&quot;10&quot;&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;duration days=&quot;14&quot;&gt;&lt;/duration&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;extrafield name=&quot;Reed_InSec&quot; parent=&quot;52&quot;&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;item id=&quot;56&quot; /&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;/extrafield&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;extrafield name=&quot;reed_location&quot;&gt;38&lt;/extrafield&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;extrafield name=&quot;reed_cboListingType&quot;&gt;1&lt;/extrafield&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;extrafield name=&quot;reed_hidesal&quot;&gt;1&lt;/extrafield&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;/board&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;board id=&quot;41&quot;&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;duration days=&quot;2&quot;&gt;&lt;/duration&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;extrafield name=&quot;JS_Industries&quot;&gt;IT&lt;/extrafield&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;extrafield name=&quot;JS_Salary&quot;&gt;No benefits&lt;/extrafield&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;extrafield name=&quot;jobsiteStartDate&quot;&gt;Immediate&lt;/extrafield&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;extrafield name=&quot;jobsite_anyjobs&quot;&gt;E&lt;/extrafield&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;extrafield name=&quot;JS_url_app&quot;&gt;http://somesite.com/example_app_url.htm&lt;/extrafield&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;extrafield name=&quot;js_oloc&quot;&gt;Greater London Area&lt;/extrafield&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;/board&gt;
&nbsp;&nbsp;&lt;/posts&gt;
&nbsp;&lt;/job&gt;
&lt;/idibu&gt;
</code></pre>
<p>Whenever something is changed in order to demonstrate an example, add only the part of the payload that is changed, removed or added, surrounded by the two XML comment lines with 3 dots on each, like this:</p>
<pre>
<code>
<!-- ... -->
&nbsp;&nbsp;&lt;/config&gt;
&nbsp;&nbsp;&lt;job&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;sender id=&quot;31000383&quot;&gt;&lt;/sender&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;!-- we add the dynamic core field app_url --&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;app_url&gt;http://somesite.com/example_app_url.htm&lt;/app_url&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;title&gt;&lt;![CDATA[Here goes the job title]]&gt;&lt;/title&gt;
&lt;!-- ... --&gt;
</code></pre>
<p>Our tests will use 3 boards to show different usages of the API: idibu Dev Board (A board that we make available to all our clients so they can through fully test the posting process, board id 517), Reed (board id 10) and Jobsite.co.uk (board id 41). Some of the extra fields and mappings that are related to these boards will be changed or added explicitly for the purpose of some tests. Please refer to the <a href="/docs/job-board-data">board discovery services</a> for each board to have accurate information for the boards.</p>
<p><strong>If you use the XML that you find in this page without checking that service first, your request might fail or return unexpected results.</strong></p>
<p><b>Repost example</b></p>
<p>A successful post will return you a success message:</p>
<pre>
<code>
&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot; ?&gt;
&lt;idibu&gt;
&nbsp;&lt;job status=&quot;added&quot; id=&quot;31003549&quot;&gt;
&nbsp;&nbsp;&lt;posts&gt;
&nbsp;&nbsp;&nbsp;&lt;posts status=&quot;pending&quot; boardid=&quot;10&quot; queueid=&quot;2127&quot; type=&quot;add&quot; publish=&quot;2011-11-26 00:01&quot; duration=&quot;14&quot; /&gt;
&nbsp;&nbsp;&nbsp;&lt;posts status=&quot;pending&quot; boardid=&quot;56&quot; queueid=&quot;2128&quot; type=&quot;add&quot; publish=&quot;2011-11-26 00:01&quot; duration=&quot;7&quot; /&gt;
&nbsp;&nbsp;&nbsp;&lt;posts status=&quot;pending&quot; boardid=&quot;517&quot; queueid=&quot;2129&quot; type=&quot;add&quot; publish=&quot;2011-11-26 00:01&quot; duration=&quot;28&quot; /&gt;
&nbsp;&nbsp;&lt;/posts&gt;
&nbsp;&lt;/job&gt;
&nbsp;&lt;log&gt;
&nbsp;&nbsp;&nbsp;&lt;warnings&gt;
&nbsp;&nbsp;&lt;!-- extra_field_warning_CiL_Salary_0 extra_field --&gt; &lt;warning field=&#39;CiL_Salary&#39; type=&#39;hidden&#39; boardid=&#39;56&#39; required=&#39;no&#39;&gt;Field &#39;CiL_Salary&#39; is missing, an empty string, or contains only whitespace.&lt;/warning&gt;
&nbsp;&nbsp;&lt;!-- extra_field_warning_carinlo_odat_0 extra_field --&gt; &lt;warning field=&#39;carinlo_odat&#39; type=&#39;hidden&#39; boardid=&#39;56&#39; required=&#39;no&#39;&gt;Field &#39;carinlo_odat&#39; is missing, an empty string, or contains only whitespace.&lt;/warning&gt;
&nbsp;&nbsp;&lt;!-- extra_field_warning_carinlo_oloc_0 extra_field --&gt; &lt;warning field=&#39;carinlo_oloc&#39; type=&#39;text&#39; boardid=&#39;56&#39; required=&#39;no&#39;&gt;Field &#39;carinlo_oloc&#39; is missing, an empty string, or contains only whitespace.&lt;/warning&gt;
&nbsp;&nbsp;&lt;!-- extra_field_warning_dev_board_app_url_0 extra_field --&gt; &lt;warning field=&#39;dev_board_app_url&#39; type=&#39;text&#39; boardid=&#39;517&#39; required=&#39;no&#39;&gt;Field &#39;dev_board_app_url&#39; is missing, an empty string, or contains only whitespace.&lt;/warning&gt;
&nbsp;&nbsp;&lt;!-- extra_field_warning_idibudts_cat_0 extra_field --&gt; &lt;warning field=&#39;idibudts_cat&#39; type=&#39;select&#39; boardid=&#39;517&#39; required=&#39;yes&#39; mapped=&#39;yes&#39;&gt;Field &#39;idibudts_cat&#39; was missing from the payload, but was mapped internally by the system&lt;/warning&gt;
&nbsp;&nbsp;&lt;!-- extra_field_warning_idibu_salary_0 extra_field --&gt; &lt;warning field=&#39;idibu_salary&#39; type=&#39;text&#39; boardid=&#39;517&#39; required=&#39;no&#39;&gt;Field &#39;idibu_salary&#39; is missing, an empty string, or contains only whitespace.&lt;/warning&gt;
&nbsp;&nbsp;&lt;!-- extra_field_warning_Reed_InSec_0 extra_field --&gt; &lt;warning field=&#39;Reed_InSec&#39; type=&#39;doubleSelect&#39; boardid=&#39;10&#39; required=&#39;yes&#39; mapped=&#39;yes&#39;&gt;Field &#39;Reed_InSec&#39; was missing from the payload, but was mapped internally by the system&lt;/warning&gt;
&nbsp;&nbsp;&lt;!-- extra_field_warning_reed_location_0 extra_field --&gt; &lt;warning field=&#39;reed_location&#39; type=&#39;select&#39; boardid=&#39;10&#39; required=&#39;yes&#39; mapped=&#39;yes&#39;&gt;Field &#39;reed_location&#39; was missing from the payload, but was mapped internally by the system&lt;/warning&gt;
&nbsp;&nbsp;&lt;!-- extra_field_warning_reed_cboListingType_0 extra_field --&gt; &lt;warning field=&#39;reed_cboListingType&#39; type=&#39;select&#39; boardid=&#39;10&#39; required=&#39;no&#39;&gt;Field &#39;reed_cboListingType&#39; is missing, an empty string, or contains only whitespace.&lt;/warning&gt;
&nbsp;&nbsp;&lt;!-- extra_field_warning_reed_hidesal_0 extra_field --&gt; &lt;warning field=&#39;reed_hidesal&#39; type=&#39;select&#39; boardid=&#39;10&#39; required=&#39;no&#39;&gt;Field &#39;reed_hidesal&#39; is missing, an empty string, or contains only whitespace.&lt;/warning&gt;
&nbsp;&lt;/warnings&gt;
&nbsp;&lt;/log&gt;
&lt;/idibu&gt;
</code></pre>
<p>So reposting this job would need an XML such as the below one:</p>
<pre>
<code>

&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot;?&gt;
&lt;idibu&gt;
&nbsp;&lt;!-- Posting (update) with all required extra fields. Will not return PCP, as boards are locked.
&nbsp;&nbsp;WARNING: Job ID and Sender ID based on previous response and Consultans discovery service    --&gt;
&nbsp;&lt;method&gt;update&lt;/method&gt;
&nbsp;&lt;config&gt;
&nbsp;&nbsp;&lt;show_durations&gt;no&lt;/show_durations&gt;
&nbsp;&nbsp;&lt;completionurl&gt;email&lt;/completionurl&gt;
&nbsp;&nbsp;&lt;advertcompletionemail&gt;admin@email.com&lt;/advertcompletionemail&gt;
&nbsp;&nbsp;&lt;lockboards&gt;yes&lt;/lockboards&gt;
&nbsp;&nbsp;&lt;redirecturl&gt;http://www.google.com&lt;/redirecturl&gt;
&nbsp;&nbsp;&lt;validate_level&gt;warning&lt;/validate_level&gt;
&nbsp;&lt;/config&gt;
&nbsp;&lt;job id=&quot;31003549&quot;&gt;&lt;!-- Job ID fetched from previous response --&gt;
&nbsp;&nbsp;&lt;title&gt;&lt;![CDATA[XML API V3 test]]&gt;&lt;/title&gt;
&nbsp;&nbsp;&lt;reference&gt;XAV3-test&lt;/reference&gt;
&nbsp;&nbsp;&lt;description&gt;&lt;![CDATA[XML API V3 test, please ignore]]&gt;&lt;/description&gt;
&nbsp;&nbsp;&lt;sender id=&quot;32000065&quot; /&gt;&lt;!-- Sender DI fetched from discovery service --&gt;
&nbsp;&nbsp;&lt;category id=&quot;21&quot; /&gt;
&nbsp;&nbsp;&lt;location id=&quot;8&quot; /&gt;
&nbsp;&nbsp;&lt;sublocation id=&quot;668&quot; /&gt;
&nbsp;&nbsp;&lt;jobtype id=&quot;2&quot; /&gt;
&nbsp;&nbsp;&lt;startdate&gt;2011-11-26&lt;/startdate&gt;
&nbsp;&nbsp;&lt;duration&gt;Full time&lt;/duration&gt;
&nbsp;&nbsp;&lt;salarymin&gt;20000&lt;/salarymin&gt;
&nbsp;&nbsp;&lt;salarymax&gt;25000&lt;/salarymax&gt;
&nbsp;&nbsp;&lt;salaryper value=&quot;annum&quot; /&gt;
&nbsp;&nbsp;&lt;currency&gt;GBP&lt;/currency&gt;
&nbsp;&nbsp;&lt;publish&gt;2011-11-26&lt;/publish&gt;
&nbsp;&nbsp;&lt;posts&gt;
&nbsp;&nbsp;&nbsp;&lt;board id=&quot;517&quot;&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;duration days=&quot;28&quot; /&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&lt;extrafield name=&#39;idibudts_cat&#39;&gt;9&lt;/extrafield&gt;
&nbsp;&nbsp;&nbsp;&lt;/board&gt;
&nbsp;&nbsp;&lt;/posts&gt;
&nbsp;&lt;/job&gt;
&lt;/idibu&gt;

</code></pre>
<p>Below is an example using know special characters, that usually cause formatting issues:</p>
<pre>
<code>
&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot;?&gt;
&lt;idibu&gt;
&lt;method&gt;add&lt;/method&gt;
&lt;config&gt;
&lt;show_durations&gt;no&lt;/show_durations&gt;
&lt;completionurl&gt;email&lt;/completionurl&gt;
&lt;advertcompletionemail&gt;bob@bob.com&lt;/advertcompletionemail&gt;
&lt;lockboards&gt;yes&lt;/lockboards&gt;
&lt;redirecturl&gt;http://www.google.com &lt;/redirecturl&gt;
&lt;validate_level&gt;warning&lt;/validate_level&gt;
&lt;/config&gt;
&lt;job&gt;
&lt;title&gt;&lt;![CDATA[XML v 3 test, please ignore Special &#163; $ &amp; % @ ! ? . , = ) ( - : ; _ + &#39; &quot; €]]&gt;&lt;/title&gt;
&lt;reference&gt;ABC123456789&lt;/reference&gt;
&lt;description&gt;&lt;![CDATA[&lt;b&gt;Special Te &#163; $ &amp; % @ ! ? . , = ) ( / - : ; _ + &#39; &quot; &#39; here euro € 
Basic Te &#163; $ &amp; % @ ! ? . , = ) ( / - : ; _ + &#39; &quot; &#39; € 
Special Te &#163; $ &amp; % @ ! ? . , = ) ( / - : ; _ + &#39; &quot; &#39; € 

 
 Special Te &#163; $ &amp; % @ ! ? . , = ) ( / - : ; _ + &#39; &quot; &#39; € 
Basic Te &#163; $ &amp; % @ ! ? . , = ) ( / - : ; _ + &#39; &quot; &#39; € 

 – – ’ &#39; •       , 	, • &#183; “ ” &#216; … &#168; &#166; &#39; : &#39; ƒ &#225; ‘ &#186; &#161; &#167; &#233; &#215; ‡ &#39; : &#39; &#39; &#199; &#189; „ h &#174; — &#172; ƒ &#225; ™&lt;/b&gt;]]&gt;&lt;/description&gt;
&lt;sender&gt;
&lt;name&gt;Steve&lt;/name&gt;
&lt;lastname&gt;Rogers&lt;/lastname&gt;
&lt;email&gt;test@mail.net&lt;/email&gt;
&lt;company&gt;One World Market&lt;/company&gt;
&lt;phone&gt;44 (0) 111-1111111&lt;/phone&gt;
&lt;www&gt;http://uk.idibu.com &lt;/www&gt;
&lt;country&gt;UK&lt;/country&gt;
&lt;postcode&gt;020 1111 1111&lt;/postcode&gt;
&lt;/sender&gt;
&lt;category id=&quot;21&quot; /&gt;
&lt;location id=&quot;8&quot; /&gt;
&lt;sublocation id=&quot;668&quot; /&gt;
&lt;jobtype id=&quot;2&quot; /&gt;
&lt;job_time&gt;2&lt;/job_time&gt;
&lt;startdate&gt;2011-11-26&lt;/startdate&gt;
&lt;duration&gt;Full time&lt;/duration&gt;
&lt;salarymin&gt;20000&lt;/salarymin&gt;
&lt;salarymax&gt;25000&lt;/salarymax&gt;
&lt;salaryper value=&quot;annum&quot; /&gt;
&lt;salaryOverride&gt;Salary override test test&lt;/salaryOverride&gt;
&lt;currency&gt;GBP&lt;/currency&gt;
&lt;publish&gt;2011-11-26&lt;/publish&gt;
&lt;posts&gt;
&lt;board id=&quot;517&quot;&gt;
&lt;extrafield name=&quot;idibudts_cat&quot;&gt;3&lt;/extrafield&gt;
&lt;duration days=&quot;7&quot; /&gt;
&lt;/board&gt;
&lt;/posts&gt;
&lt;/job&gt;
&lt;/idibu&gt;
</code></pre>
<p>And how it should like correctly URL encoded following the rules set in <a href="http://www.idibuworld.com/docs/submitting-and-responses">Submitting and Responses</a> section:</p>
<pre>
<code>
xml_text=%3C%3Fxml+version%3D%221.0%22+encoding%3D%22UTF-8%22%3F%3E%0D%0A%3Cidibu%3E%0D%0A%3Cmethod%3Eadd%3C%2Fmethod%3E%0D%0A%3Cconfig%3E%0D%0A%3Cshow_durations%3Eno%3C%2Fshow_durations%3E%0D%0A%3Ccompletionurl%3Eemail%3C%2Fcompletionurl%3E%0D%0A%3Cadvertcompletionemail%3Ebob%40bob.com%3C%2Fadvertcompletionemail%3E%0D%0A%3Clockboards%3Eyes%3C%2Flockboards%3E%0D%0A%3Credirecturl%3Ehttp%3A%2F%2Fwww.google.com+%3C%2Fredirecturl%3E%0D%0A%3Cvalidate_level%3Ewarning%3C%2Fvalidate_level%3E%0D%0A%3C%2Fconfig%3E%0D%0A%3Cjob%3E%0D%0A%3Ctitle%3E%3C%21%5BCDATA%5BXML+v+3+test%2C+please+ignore+Special+%A3+%24+%26+%25+%40+%21+%3F+.+%2C+%3D+%29+%28+-+%3A+%3B+_+%2B+%27+%22+%80%5D%5D%3E%3C%2Ftitle%3E%0D%0A%3Creference%3EABC123456789%3C%2Freference%3E%0D%0A%3Cdescription%3E%3C%21%5BCDATA%5B%3Cb%3ESpecial+Te+%A3+%24+%26+%25+%40+%21+%3F+.+%2C+%3D+%29+%28+%2F+-+%3A+%3B+_+%2B+%27+%22+%27+here+euro+%80+%0D%0ABasic+Te+%A3+%24+%26+%25+%40+%21+%3F+.+%2C+%3D+%29+%28+%2F+-+%3A+%3B+_+%2B+%27+%22+%27+%80+%0D%0ASpecial+Te+%A3+%24+%26+%25+%40+%21+%3F+.+%2C+%3D+%29+%28+%2F+-+%3A+%3B+_+%2B+%27+%22+%27+%80+%0D%0A%0D%0A+%0D%0A+Special+Te+%A3+%24+%26+%25+%40+%21+%3F+.+%2C+%3D+%29+%28+%2F+-+%3A+%3B+_+%2B+%27+%22+%27+%80+%0D%0ABasic+Te+%A3+%24+%26+%25+%40+%21+%3F+.+%2C+%3D+%29+%28+%2F+-+%3A+%3B+_+%2B+%27+%22+%27+%80+%0D%0A%0D%0A+%96+%96+%92+%27+%95+++++++%2C+%09%2C+%95+%B7+%93+%94+%D8+%85+%A8+%A6+%27+%3A+%27+%83+%E1+%91+%BA+%A1+%A7+%E9+%D7+%87+%27+%3A+%27+%27+%C7+%BD+%84+h+%AE+%97+%AC+%83+%E1+%99%3C%2Fb%3E%5D%5D%3E%3C%2Fdescription%3E%0D%0A%3Csender%3E%0D%0A%3Cname%3ESteve%3C%2Fname%3E%0D%0A%3Clastname%3ERogers%3C%2Flastname%3E%0D%0A%3Cemail%3Etest%40mail.net%3C%2Femail%3E%0D%0A%3Ccompany%3EOne+World+Market%3C%2Fcompany%3E%0D%0A%3Cphone%3E44+%280%29+111-1111111%3C%2Fphone%3E%0D%0A%3Cwww%3Ehttp%3A%2F%2Fuk.idibu.com+%3C%2Fwww%3E%0D%0A%3Ccountry%3EUK%3C%2Fcountry%3E%0D%0A%3Cpostcode%3E020+1111+1111%3C%2Fpostcode%3E%0D%0A%3C%2Fsender%3E%0D%0A%3Ccategory+id%3D%2221%22+%2F%3E%0D%0A%3Clocation+id%3D%228%22+%2F%3E%0D%0A%3Csublocation+id%3D%22668%22+%2F%3E%0D%0A%3Cjobtype+id%3D%222%22+%2F%3E%0D%0A%3Cjob_time%3E2%3C%2Fjob_time%3E%0D%0A%3Cstartdate%3E2011-11-26%3C%2Fstartdate%3E%0D%0A%3Cduration%3EFull+time%3C%2Fduration%3E%0D%0A%3Csalarymin%3E20000%3C%2Fsalarymin%3E%0D%0A%3Csalarymax%3E25000%3C%2Fsalarymax%3E%0D%0A%3Csalaryper+value%3D%22annum%22+%2F%3E%0D%0A%3CsalaryOverride%3ESalary+override+test+test%3C%2FsalaryOverride%3E%0D%0A%3Ccurrency%3EGBP%3C%2Fcurrency%3E%0D%0A%3Cpublish%3E2011-11-26%3C%2Fpublish%3E%0D%0A%3Cposts%3E%0D%0A%3Cboard+id%3D%22517%22%3E%0D%0A%3Cextrafield+name%3D%22idibudts_cat%22%3E3%3C%2Fextrafield%3E%0D%0A%3Cduration+days%3D%227%22+%2F%3E%0D%0A%3C%2Fboard%3E%0D%0A%3C%2Fposts%3E%0D%0A%3C%2Fjob%3E%0D%0A%3C%2Fidibu%3E
</code></pre>
