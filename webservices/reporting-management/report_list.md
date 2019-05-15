This service allows you to view all available reports.

```bash
GET: ws.idibu.com/ws/rest/v1/reports?hash=CLIENTS_HASH
```

<h2>Response</h2>


```xml
<?xml version="1.0" encoding="UTF-8"?>
<idibu generator="idibu" version="1.0">
  <response>
    <reports>
      <report>
        <id>status</id>
        <type>activity</type>
        <name>Aptrack Status Analysis</name>
        <knowledgebase-url>
http://v2-docs.idibu.com/article/116-breakdown-of-idibu-downloadable-reports#aptrack_status_analysis
        </knowledgebase-url>
      </report>
      <report>
        <id>budget</id>
        <type>activity</type>
        <name>Board Budget Report</name>
        <knowledgebase-url>
http://v2-docs.idibu.com/article/116-breakdown-of-idibu-downloadable-reports#board_budget_report
        </knowledgebase-url>
      </report>
      <report>
        <id>boardactivity</id>
        <type>activity</type>
        <name>Board Detail Performance</name>
        <knowledgebase-url>
http://v2-docs.idibu.com/article/116-breakdown-of-idibu-downloadable-reports#board_detail_performance
        </knowledgebase-url>
      </report>
      <report>
        <id>detail</id>
        <type>activity</type>
        <name>Consultant Activity Detail</name>
        <knowledgebase-url>
http://v2-docs.idibu.com/article/116-breakdown-of-idibu-downloadable-reports#consultant_activity_detail
        </knowledgebase-url>
      </report>
      <report>
        <id>comparision</id>
        <type>activity</type>
        <name>Consultant Comparison</name>
        <knowledgebase-url>
http://v2-docs.idibu.com/article/116-breakdown-of-idibu-downloadable-reports#consultant_comparison
        </knowledgebase-url>
      </report>
      <report>
        <id>access</id>
        <type>activity</type>
        <name>CV Auto Login Access Logs</name>
        <knowledgebase-url>
http://v2-docs.idibu.com/article/116-breakdown-of-idibu-downloadable-reports#cv_search_access_logs
        </knowledgebase-url>
      </report>
      <report>
        <id>job</id>
        <type>activity</type>
        <name>Jobs Posted</name>
        <knowledgebase-url>
http://v2-docs.idibu.com/article/116-breakdown-of-idibu-downloadable-reports#jobs_posted
        </knowledgebase-url>
      </report>
      <report>
        <id>board</id>
        <type>activity</type>
        <name>System Activity Detail</name>
        <knowledgebase-url>
http://v2-docs.idibu.com/article/116-breakdown-of-idibu-downloadable-reports#system_activity_detail
        </knowledgebase-url>
      </report>
      <report>
        <id>sector</id>
        <type>activity</type>
        <name>System Based Application Breakdown</name>
        <knowledgebase-url>
http://v2-docs.idibu.com/article/116-breakdown-of-idibu-downloadable-reports#sector_based_application_breakdown
        </knowledgebase-url>
      </report>
      <report>
        <id>summary</id>
        <type>activity</type>
        <name>System Activity Summary</name>
        <knowledgebase-url>
http://v2-docs.idibu.com/article/116-breakdown-of-idibu-downloadable-reports#system_activity_summary
        </knowledgebase-url>
      </report>
      <report>
        <id>usage</id>
        <type>history</type>
        <name>Historical System Usage by Month</name>
        <knowledgebase-url>
http://v2-docs.idibu.com/article/116-breakdown-of-idibu-downloadable-reports#historical_statistics
        </knowledgebase-url>
      </report>
      <report>
        <id>live</id>
        <type>current</type>
        <name>Live Adverts</name>
        <knowledgebase-url>
http://v2-docs.idibu.com/article/116-breakdown-of-idibu-downloadable-reports#live_adverts
        </knowledgebase-url>
      </report>
      <report>
        <id>quota</id>
        <type>current</type>
        <name>Quota Spend</name>
        <knowledgebase-url>
http://v2-docs.idibu.com/article/116-breakdown-of-idibu-downloadable-reports#quota_spent
        </knowledgebase-url>
      </report>
      <report>
        <id>breakdown</id>
        <type>applicant</type>
        <name>Applicant Breakdown Detail</name>
        <knowledgebase-url>
http://v2-docs.idibu.com/article/116-breakdown-of-idibu-downloadable-reports#applicant_breakdown_detail
        </knowledgebase-url>
      </report>
      <report>
        <id>analysis</id>
        <type>applicant</type>
        <name>Application Analysis</name>
        <knowledgebase-url>
http://v2-docs.idibu.com/article/116-breakdown-of-idibu-downloadable-reports#application_analysis
        </knowledgebase-url>
      </report>
      <report>
        <id>countperjob</id>
        <type>applicant</type>
        <name>Applicant Count per Job</name>
        <knowledgebase-url>
http://v2-docs.idibu.com/article/116-breakdown-of-idibu-downloadable-reports#applicant_count_per_job
        </knowledgebase-url>
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
