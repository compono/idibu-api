This service allows you to view all available reports.
<pre>
<code>
GET: ws.idibu.com/ws/rest/v1/reports?hash=CLIENTS_HASH
</code></pre>
<h2>
	Response</h2>


```xml

<?xml version="1.0" encoding="UTF-8"?>
<idibu generator="idibu" version="1.0">
  <response>
    <reports>
      <report>
        <id>status</id>
        <type>activity</type>
        <name>Aptrack Status Analysis</name>
        <knowledgebase-url>http://support.idibu.com/default_import/Knowledgebase/Article/View/94/0/breakdown-of-idibu-downloadable-reports#1. Aptrack Status Analysis</knowledgebase-url>
      </report>
      <report>
        <id>budget</id>
        <type>activity</type>
        <name>Board Budget Report</name>
        <knowledgebase-url>http://support.idibu.com/default_import/Knowledgebase/Article/View/94/0/breakdown-of-idibu-downloadable-reports#10.budget</knowledgebase-url>
      </report>
      <report>
        <id>boardactivity</id>
        <type>activity</type>
        <name>Board Detail Performance</name>
        <knowledgebase-url>http://support.idibu.com/default_import/Knowledgebase/Article/View/94/0/breakdown-of-idibu-downloadable-reports#8. Board Details Performance</knowledgebase-url>
      </report>
      <report>
        <id>detail</id>
        <type>activity</type>
        <name>Consultant Activity Detail</name>
        <knowledgebase-url>http://support.idibu.com/default_import/Knowledgebase/Article/View/94/0/breakdown-of-idibu-downloadable-reports#2. Consultant Activity Detail</knowledgebase-url>
      </report>
      <report>
        <id>comparision</id>
        <type>activity</type>
        <name>Consultant Comparison</name>
        <knowledgebase-url>http://support.idibu.com/default_import/Knowledgebase/Article/View/94/0/breakdown-of-idibu-downloadable-reports#3. Consultant Comparison</knowledgebase-url>
      </report>
      <report>
        <id>job</id>
        <type>activity</type>
        <name>Jobs Posted</name>
        <knowledgebase-url>http://support.idibu.com/default_import/Knowledgebase/Article/View/94/0/breakdown-of-idibu-downloadable-reports#5. Jobs Posted</knowledgebase-url>
      </report>
      <report>
        <id>board</id>
        <type>activity</type>
        <name>System Activity Detail</name>
        <knowledgebase-url>http://support.idibu.com/default_import/Knowledgebase/Article/View/94/0/breakdown-of-idibu-downloadable-reports#6. System Activity Detail</knowledgebase-url>
      </report>
      <report>
        <id>sector</id>
        <type>activity</type>
        <name>System Based Application Breakdown</name>
        <knowledgebase-url>http://support.idibu.com/default_import/Knowledgebase/Article/View/94/0/breakdown-of-idibu-downloadable-reports#9. sbsab</knowledgebase-url>
      </report>
      <report>
        <id>summary</id>
        <type>activity</type>
        <name>System Activity Summary</name>
        <knowledgebase-url>http://support.idibu.com/default_import/Knowledgebase/Article/View/94/0/breakdown-of-idibu-downloadable-reports#7. System Activity Summary</knowledgebase-url>
      </report>
      <report>
        <id>usage</id>
        <type>history</type>
        <name>Historical System Usage by Month</name>
        <knowledgebase-url>http://support.idibu.com/default_import/Knowledgebase/Article/View/94/0/breakdown-of-idibu-downloadable-reports#Report type =&gt; Historical Statistics</knowledgebase-url>
      </report>
      <report>
        <id>live</id>
        <type>current</type>
        <name>Live Adverts</name>
        <knowledgebase-url>http://support.idibu.com/default_import/Knowledgebase/Article/View/94/0/breakdown-of-idibu-downloadable-reports#1. Live Adverts</knowledgebase-url>
      </report>
      <report>
        <id>quota</id>
        <type>current</type>
        <name>Quota Spend</name>
        <knowledgebase-url>http://support.idibu.com/default_import/Knowledgebase/Article/View/94/0/breakdown-of-idibu-downloadable-reports#2. Quota Spend</knowledgebase-url>
      </report>
      <report>
        <id>breakdown</id>
        <type>applicant</type>
        <name>Applicant Breakdown Detail</name>
        <knowledgebase-url>http://support.idibu.com/default_import/Knowledgebase/Article/View/94/0/breakdown-of-idibu-downloadable-reports#1. Applicant Breakdown Detail</knowledgebase-url>
      </report>
      <report>
        <id>analysis</id>
        <type>applicant</type>
        <name>Application Analysis</name>
        <knowledgebase-url>http://support.idibu.com/default_import/Knowledgebase/Article/View/94/0/breakdown-of-idibu-downloadable-reports#2. Application Analysis</knowledgebase-url>
      </report>
    </reports>
    <report-types>
      <report-type>
        <id>activity</id>
        <name>Activity reports</name>
        <options>
          <option>date-range</option>
          <option>profiles</option>
          <option>boards</option>
        </options>
      </report-type>
      <report-type>
        <id>history</id>
        <name>Historical statistics</name>
        <options/>
      </report-type>
      <report-type>
        <id>current</id>
        <name>Current statistics</name>
        <options>
          <option>profiles</option>
          <option>boards</option>
        </options>
      </report-type>
      <report-type>
        <id>applicant</id>
        <name>Applicant reports</name>
        <options>
          <option>date-range</option>
          <option>profiles</option>
          <option>boards</option>
        </options>
      </report-type>
    </report-types>
  </response>
  <status>success</status>
</idibu>

```


