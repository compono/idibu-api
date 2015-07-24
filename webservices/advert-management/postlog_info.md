<p>Method returns detailed advert posting logs information for given post id. The information is not unified and is unique per job board. Post Id can be obtained via ad details ws.</p>
<h2>
	Request</h2>
<pre>
<code>
/ws/rest/v1/posting-logs/[PostLogID]
</code></pre>
<h2>
	Examples Responses</h2>
<pre>
Reed (Board ID: 10):

&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
  &lt;response&gt;
    &lt;log&gt;
      &lt;id&gt;2932262&lt;/id&gt;
      &lt;portal&gt;10&lt;/portal&gt;
      &lt;type&gt;success&lt;/type&gt;
      &lt;created&gt;2015-07-24 12:02:08&lt;/created&gt;
      &lt;job&gt;
        &lt;id&gt;260356&lt;/id&gt;
        &lt;title&gt;Service Engineer&lt;/title&gt;
        &lt;reference&gt;SP1507-46/3&lt;/reference&gt;
      &lt;/job&gt;
      &lt;request&gt;&lt;![CDATA[txtService=ONEWORLD&amp;txtUserName=loginname&amp;txtPassword=password&amp;txtEmail=apply.a31kd1qujq@aptrack.co.uk&amp;txtRef=SP1507-46%2F3&amp;txtExpiry=42&amp;txtDuration=n%2Fa&amp;txtJobTitle=Service+Engineer&amp;optForGrad=&amp;txtSalMin=30000&amp;txtSalMax=35000&amp;cboSalaryType=5&amp;memDescription=Join+a+worldwide+market+leading+manufacturer+of+packaging+machinery+solutions+supplying+the+food+industry.+Due+to+growth+they+need+to+strengthen+their+service+team+covering+the+UK+and+want+to+recruit+experienced+qualified+%26+commercially+aware+service+engineers.%0D%0A%0D%0A+BASIC%3A+up+to+%C2%A335%2C000%0D%0A%0D%0A+ADDITIONAL+BENEFITS%3A+%2B+Overtime+%26+Bonuses+to+earn+up+to+%C2%A310%2C000+on+top+of+base+%2B+Choice+of+car+%2B+5%25+Pension%0D%0A%0D%0A+LOCATION%3A+Covering+the+UK+%26+home+based+so+living+anywhere+between+the+M62+%26+M4+corridors%0D%0A%0D%0A+COMMUTABLE+LOCATIONS%3A+Birmingham%2C+Manchester%2C+Leeds%2C+Bristol%0D%0A%0D%0A+COMPANY+PROFILE%3A%0D%0A%0D%0A+A+worldwide+market+leading+manufacturer+of+packaging+machinery+solutions+supplying+the+food+industry%0D%0A%0D%0A+JOB+SPECIFICATION%3A+Service+Engineer%0D%0A%0D%0A+Classic+service+engineer+role+handling+repairs%2C+refurbishment+%26+installations+with+a+blue+chip+established+client+base.+You+will+be+expected+to+work+overtime+when+required+and+weekends+on+a+rota+basis.%0D%0A%0D%0A+REQUIREMENTS%3A+Service+Engineer%0D%0A%0D%0A+%2A+You+MUST+be+an+experienced+and+proven+field+Service+Engineer%0D%0A%2A+Ideally+with+packaging+or+process+machinery+experience+within+the+food+market%0D%0A%2A+You+WILL+be+a+qualified+electrical+%26%2For+electronic+engineer+%28ideally+to+HNC+level%29%0D%0A%2A+You+will+be+commercially+aware%2C+prepared+to+put+the+hours+in+and+stay+away+from+home+when+required%0D%0A%2A+The+company+will+consider+those+who+have+specific+experience+of+packaging+machinery+as+a+maintenance+engineer+for+a+food+company+who+want+to+move+into+a+field+service+engineer+role%0D%0A%0D%0A+INTERESTED%3F+Please+email+our+retained+consultant+Stuart+Platt+quoting+Service+Engineer+UK+and+reference+SP1507-46+to+Wallace+Hind+Selection.+The+Old+Vicarage.+Duston.+Northants.+NN5+6JB.+Tel%3A+01604+758857+Please+note+that+the+postcodes+used+for+this+vacancy+are+for+searching+purposes+only%2C+they+may+not+refer+exactly+to+where+the+role+is+based.%0D%0A%0D%0A+%C2%A0&amp;cboType=1&amp;txtTown=BS1%206QF&amp;cboCurrency=1&amp;cboCounty=266&amp;chkSalNegotiableHide=&amp;chkHdnSalaryDescription=&amp;cboSector=202&amp;cboWorkingHours=1&amp;txtExternalApplicationURL=&amp;cboListingType=2&amp;oldlistingdebug=2]]&gt;&lt;/request&gt;
      &lt;response&gt;&lt;![CDATA[


SUCCESS

JobID=1234567

]]&gt;&lt;/response&gt;
    &lt;/log&gt;
  &lt;/response&gt;
  &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;

Total Jobs (Board ID: 15):

&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
  &lt;response&gt;
    &lt;log&gt;
      &lt;id&gt;2932261&lt;/id&gt;
      &lt;portal&gt;15&lt;/portal&gt;
      &lt;type&gt;success,warn&lt;/type&gt;
      &lt;created&gt;2015-07-24 12:02:06&lt;/created&gt;
      &lt;job&gt;
        &lt;id&gt;260356&lt;/id&gt;
        &lt;title&gt;Service Engineer&lt;/title&gt;
        &lt;reference&gt;SP1507-46/3&lt;/reference&gt;
      &lt;/job&gt;
      &lt;request&gt;&lt;![CDATA[xmlData=%3CFILE%3E%0D%0A%3CADVERT%3E%0D%0A%3CROOT+LOADTYPE%3D%22A%22%3E%0D%0A%3CJOB+FEEDID%3D%22DB00000001%22+%0D%0ALIVEDAYS%3D%2214%22+%0D%0AUNIQUEJOBNO%3D%225795SP1507-46%2F3%22+%0D%0ADESCRIPTION%3D%22%26lt%3Bp%26gt%3BJoin+a+worldwide+market+leading+manufacturer+of+packaging+machinery+solutions+supplying+the+food+industry.+Due+to+growth+they+need+to+strengthen+their+service+team+covering+the+UK+and+want+to+recruit+experienced+qualified+%26amp%3B+commercially+aware+service+engineers.%26lt%3B%2Fp%26gt%3B%0D%0A%26lt%3Bp%26gt%3BBASIC%3A+up+to+%26%23163%3B35%2C000%26lt%3B%2Fp%26gt%3B%0D%0A%26lt%3Bp%26gt%3BADDITIONAL+BENEFITS%3A+%2B+Overtime+%26amp%3B+Bonuses+to+earn+up+to+%26%23163%3B10%2C000+on+top+of+base+%2B+Choice+of+car+%2B+5%25+Pension%26lt%3B%2Fp%26gt%3B%0D%0A%26lt%3Bp%26gt%3BLOCATION%3A+Covering+the+UK+%26amp%3B+home+based+so+living+anywhere+between+the+M62+%26amp%3B+M4+corridors%26lt%3B%2Fp%26gt%3B%0D%0A%26lt%3Bp%26gt%3BCOMMUTABLE+LOCATIONS%3A+Birmingham%2C+Manchester%2C+Leeds%2C+Bristol%26lt%3B%2Fp%26gt%3B%0D%0A%26lt%3Bp%26gt%3BCOMPANY+PROFILE%3A%26lt%3B%2Fp%26gt%3B%0D%0A%26lt%3Bp%26gt%3BA+worldwide+market+leading+manufacturer+of+packaging+machinery+solutions+supplying+the+food+industry%26lt%3B%2Fp%26gt%3B%0D%0A%26lt%3Bp%26gt%3BJOB+SPECIFICATION%3A+Service+Engineer%26lt%3B%2Fp%26gt%3B%0D%0A%26lt%3Bp%26gt%3BClassic+service+engineer+role+handling+repairs%2C+refurbishment+%26amp%3B+installations+with+a+blue+chip+established+client+base.+You+will+be+expected+to+work+overtime+when+required+and+weekends+on+a+rota+basis.%26lt%3B%2Fp%26gt%3B%0D%0A%26lt%3Bp%26gt%3BREQUIREMENTS%3A+Service+Engineer%26lt%3B%2Fp%26gt%3B%0D%0A%26lt%3Bp%26gt%3B%2A+You+MUST+be+an+experienced+and+proven+field+Service+Engineer%26lt%3Bbr%26gt%3B%2A+Ideally+with+packaging+or+process+machinery+experience+within+the+food+market%26lt%3Bbr%26gt%3B%2A+You+WILL+be+a+qualified+electrical+%26amp%3B%2For+electronic+engineer+%28ideally+to+HNC+level%29%26lt%3Bbr%26gt%3B%2A+You+will+be+commercially+aware%2C+prepared+to+put+the+hours+in+and+stay+away+from+home+when+required%26lt%3Bbr%26gt%3B%2A+The+company+will+consider+those+who+have+specific+experience+of+packaging+machinery+as+a+maintenance+engineer+for+a+food+company+who+want+to+move+into+a+field+service+engineer+role%26lt%3B%2Fp%26gt%3B%0D%0A%26lt%3Bp%26gt%3BINTERESTED%3F+Please+email+our+retained+consultant+Stuart+Platt+quoting+Service+Engineer+UK+and+reference+SP1507-46+to+Wallace+Hind+Selection.+The+Old+Vicarage.+Duston.+Northants.+NN5+6JB.+Tel%3A+01604+758857+Please+note+that+the+postcodes+used+for+this+vacancy+are+for+searching+purposes+only%2C+they+may+not+refer+exactly+to+where+the+role+is+based.%26lt%3B%2Fp%26gt%3B%0D%0A%26lt%3Bp%26gt%3B%26%23160%3B%26lt%3B%2Fp%26gt%3B%22+%0D%0ATITLE%3D%22Service+Engineer%22+%0D%0AREGION%3D%22Bristol%22+%0D%0ARATEUNIT%3D%22a%22+%0D%0ASALARYMIN%3D%2230000%22+%0D%0ASALARYMAX%3D%2234999%22+%0D%0ASALARYDESC%3D%22%26%23163%3B30000+-+%26%23163%3B35000+per+annum%2C+Benefits%3A+%2B+Overtime+%26amp%3B+Bonuses+to+earn+up+to+%26%23163%3B10%2C000+on+top+of+base+%2B+Choice+of+car+%2B+5%25+Pension%22+%0D%0AINTERNALJOBREF%3D%22SP1507-46%2F3%22+%0D%0ARESPONSEURL%3D%22%22+%0D%0APOSTCODE%3D%22BS1+6QF%22+%0D%0AINDUSTRYLONGNAME%3D%22Engineering%2C+Manufacturing%2C+Utilities%22%0D%0AJOBTEMPLATENAME%3D%22%22%0D%0AEUONLY%3D%22False%22+%2F%3E%0D%0A%3CPOSTINGCOMPANY+USERNAME%3D%22username%22+PASSWORD%3D%22pass%22+%2F%3E+%0D%0A%3CCONTACT+PHONE%3D%2201604+683320%22+%0D%0A+++++++FAX%3D%22%22+%0D%0A+++++++EMAIL%3D%22apply.a31kd1qujp%aptrack.co.uk%22+%0D%0A+++++++FIRSTNAME%3D%22Stuart+Platt%22+%2F%3E%0D%0A%3CADDITIONALJOBTYPE+INDUSTRY%3D%22Engineering%2C+Manufacturing%2C+Utilities%22+GROUP%3D%22Permanent%22+%2F%3E%0D%0A%3C%2FROOT%3E%0D%0A%3C%2FADVERT%3E%0D%0A%3C%2FFILE%3E]]&gt;&lt;/request&gt;
      &lt;response&gt;&lt;![CDATA[&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-8&quot;?&gt;
&lt;FileLine&gt;
  &lt;JobsSubmitted&gt;1&lt;/JobsSubmitted&gt;
  &lt;Error /&gt;
  &lt;BulkJobLoader&gt;
    &lt;root&gt;
      &lt;Job JobID=&quot;5795SP1507-46/3&quot;&gt;
        &lt;JobDetail type=&quot;Information&quot;&gt;
          &lt;Detail&gt;Job Load Started Jul 24 2015 12:02PM&lt;/Detail&gt;
        &lt;/JobDetail&gt;
        &lt;JobDetail type=&quot;Warning&quot;&gt;
          &lt;Detail&gt;CONTACT\@FAX number not supplied.&lt;/Detail&gt;
        &lt;/JobDetail&gt;
        &lt;JobDetail type=&quot;JobId&quot;&gt;
          &lt;Detail&gt;JobID=123&lt;/Detail&gt;
        &lt;/JobDetail&gt;
        &lt;JobDetail type=&quot;LinkUrl&quot;&gt;
          &lt;Detail&gt;www.totaljobs.com/JobSearch/JobDetails.aspx?JobID=123&lt;/Detail&gt;
        &lt;/JobDetail&gt;
        &lt;JobDetail type=&quot;Information&quot;&gt;
          &lt;Detail&gt;Job Loaded Successfully&lt;/Detail&gt;
        &lt;/JobDetail&gt;
      &lt;/Job&gt;
      &lt;Job JobID=&quot;123&quot;&gt;
        &lt;JobDetail type=&quot;Information&quot;&gt;
          &lt;Detail&gt;JobType Permanent has been added for Industry : Engineering, Manufacturing, Utilities and JobID 123&lt;/Detail&gt;
        &lt;/JobDetail&gt;
      &lt;/Job&gt;
    &lt;/root&gt;
  &lt;/BulkJobLoader&gt;
  &lt;PostingSuccess&gt;True&lt;/PostingSuccess&gt;
  &lt;RequestContent&gt;&lt;![CDATA[&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf-16&quot;?&gt;&lt;FILE&gt;&lt;ADVERT&gt;&lt;ROOT LOADTYPE=&quot;A&quot;&gt;&lt;JOB FEEDID=&quot;DB00000001&quot; LIVEDAYS=&quot;14&quot; UNIQUEJOBNO=&quot;5795SP1507-46/3&quot; DESCRIPTION=&quot;&amp;lt;p&amp;gt;Join a worldwide market leading manufacturer of packaging machinery solutions supplying the food industry. Due to growth they need to strengthen their service team covering the UK and want to recruit experienced qualified &amp;amp; commercially aware service engineers.&amp;lt;/p&amp;gt;&amp;#xD;&amp;#xA;&amp;lt;p&amp;gt;BASIC: up to &#163;35,000&amp;lt;/p&amp;gt;&amp;#xD;&amp;#xA;&amp;lt;p&amp;gt;ADDITIONAL BENEFITS: + Overtime &amp;amp; Bonuses to earn up to &#163;10,000 on top of base + Choice of car + 5% Pension&amp;lt;/p&amp;gt;&amp;#xD;&amp;#xA;&amp;lt;p&amp;gt;LOCATION: Covering the UK &amp;amp; home based so living anywhere between the M62 &amp;amp; M4 corridors&amp;lt;/p&amp;gt;&amp;#xD;&amp;#xA;&amp;lt;p&amp;gt;COMMUTABLE LOCATIONS: Birmingham, Manchester, Leeds, Bristol&amp;lt;/p&amp;gt;&amp;#xD;&amp;#xA;&amp;lt;p&amp;gt;COMPANY PROFILE:&amp;lt;/p&amp;gt;&amp;#xD;&amp;#xA;&amp;lt;p&amp;gt;A worldwide market leading manufacturer of packaging machinery solutions supplying the food industry&amp;lt;/p&amp;gt;&amp;#xD;&amp;#xA;&amp;lt;p&amp;gt;JOB SPECIFICATION: Service Engineer&amp;lt;/p&amp;gt;&amp;#xD;&amp;#xA;&amp;lt;p&amp;gt;Classic service engineer role handling repairs, refurbishment &amp;amp; installations with a blue chip established client base. You will be expected to work overtime when required and weekends on a rota basis.&amp;lt;/p&amp;gt;&amp;#xD;&amp;#xA;&amp;lt;p&amp;gt;REQUIREMENTS: Service Engineer&amp;lt;/p&amp;gt;&amp;#xD;&amp;#xA;&amp;lt;p&amp;gt;* You MUST be an experienced and proven field Service Engineer&amp;lt;br&amp;gt;* Ideally with packaging or process machinery experience within the food market&amp;lt;br&amp;gt;* You WILL be a qualified electrical &amp;amp;/or electronic engineer (ideally to HNC level)&amp;lt;br&amp;gt;* You will be commercially aware, prepared to put the hours in and stay away from home when required&amp;lt;br&amp;gt;* The company will consider those who have specific experience of packaging machinery as a maintenance engineer for a food company who want to move into a field service engineer role&amp;lt;/p&amp;gt;&amp;#xD;&amp;#xA;&amp;lt;p&amp;gt;INTERESTED? Please email our retained consultant Stuart Platt quoting Service Engineer UK and reference SP1507-46 to Wallace Hind Selection. The Old Vicarage. Duston. Northants. NN5 6JB. Tel: 01604 758857 Please note that the postcodes used for this vacancy are for searching purposes only, they may not refer exactly to where the role is based.&amp;lt;/p&amp;gt;&amp;#xD;&amp;#xA;&amp;lt;p&amp;gt; &amp;lt;/p&amp;gt;&quot; TITLE=&quot;Service Engineer&quot; REGION=&quot;Bristol&quot; RATEUNIT=&quot;a&quot; SALARYMIN=&quot;30000&quot; SALARYMAX=&quot;34999&quot; SALARYDESC=&quot;&#163;30000 - &#163;35000 per annum, Benefits: + Overtime &amp;amp; Bonuses to earn up to &#163;10,000 on top of base + Choice of car + 5% Pension&quot; INTERNALJOBREF=&quot;SP1507-46/3&quot; RESPONSEURL=&quot;&quot; POSTCODE=&quot;BS1 6QF&quot; INDUSTRYLONGNAME=&quot;Engineering, Manufacturing, Utilities&quot; JOBTEMPLATENAME=&quot;&quot; EUONLY=&quot;False&quot; /&gt;&lt;POSTINGCOMPANY USERNAME=&quot;&quot; PASSWORD=&quot;&quot; /&gt;&lt;CONTACT PHONE=&quot;01604 683320&quot; FAX=&quot;&quot; EMAIL=&quot;apply.a31kd1qujp@aptrack.co.uk&quot; FIRSTNAME=&quot;Stuart Platt&quot; /&gt;&lt;ADDITIONALJOBTYPE INDUSTRY=&quot;Engineering, Manufacturing, Utilities&quot; GROUP=&quot;Permanent&quot; /&gt;&lt;/ROOT&gt;&lt;/ADVERT&gt;&lt;/FILE&gt;]]]]&gt;&lt;![CDATA[&gt;&lt;/RequestContent&gt;
&lt;/FileLine&gt;]]&gt;&lt;/response&gt;
    &lt;/log&gt;
  &lt;/response&gt;
  &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;


</code></pre>
