# Configuration field variables
Each of these variables is to be sent in the configuration block of the XML request, which is enclosed in the `config` tag.

| Field Name | Required? | Data Type | Description |
| --- | --- | --- | --- |
| show\_durations | No  | text (Values: yes / no - Defaults to "yes") | Controls whether the posting duration fields appear by the job board logo's |
| completionurl | No  | text (values: email) | If present, the only possible value for this tag is "email" |
| advertcompletionemail | Depends | text - email address | Required if completionurl=email - this is the email address the request to complete the posting will be sent to |
| utf8\_enable | **Yes**  | text (Values: yes / no) | Indicated if you are sending data in the UTF-8 encoding. **Always set to "yes"! Non-UTF-8 posting is deprecated.** |
| lockboards | No  | text (Values: yes / no / yes\_pcp - Defaults to "no") | Controls whether the user is able to select and unselect boards on the Post Completion Page.  <br>**yes** - blocks the board selection  <br>**no** - allows to select and deselect boards  <br>**yes\_pcp** - blocks the board selection, but prevents direct posting when all required fields are present in the payload. The PCP page will therefore always be generated. |
| partnerid | No  | text (Defaults to idibu template) | Apply for a Partner ID if you want be able to control the look and feel of the Post Completion Page. |
| redirecturl | No  | text (values: 'internal', or a valid url). | The url the user is redirected to from the Post Completion Page |
| validate\_level | No  | text (Values: warning / fail - Defaults to "warning") | Determines whether the system rejects the posting if validators are violated (fail) or if only warnings are returned (warning).  <br>Refer to the `<validators>` section of [Posting Destinations Specific Data](https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/spec-data.md) |
| returnurl | No  | link | If present, the PCP generated by the API call will contain a "back" button leading to the provided link. This link should represent the URL of the partner posting process that is able to load all the core fields based on the jobid. The link will have two additional parameters attached: jobID and continue. jobID is to identify which job is being returned to and continue stores in session the PCP fields selection |
| continue | No  | text | Determines based on the value provided with the return url, which extra fields selection load when returning to PCP. |
| pcp\_preview | No  | text | Allows you to enable a "preview" button on the PCP page that provides a summary of selected idibu core fields and already selected extra fields. This page can be styled just like the PCP itself. |

# Core field variables
The below variables need to be provided in the `job` tag of the XML request.

| Field Name | Required? | Data Type | Description |
| --- | --- | --- | --- |
| client\_reference | [Depends](https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/jobidvsjobref.md) | text | Client reference; can be used to replace the job id  (for all the methods that require it: UPDATE, REPOST, QUICKREPOST, DELETE). |
| title | **Yes** - minimum 5 characters | text | Job Title. Editable (see below) |
| description | **Yes** - minimum 5 characters | longtext | Job Description. Editable (see below). **It is very imporant, that you provide the text as one block of text and any character returns are encoded as `<br/>`. Otherwise there is a risk that your ads won't be formatted correctly when posted to job boards.** |
| reference | **Yes** - minimum 4 characters | text | Job Reference. Editable (see below) |
| startdate | **Yes** | date YYYY-MM-DD (defaults to today) | The date from which the job begins (only relevant for jobs in the future. |
| duration | No  | text | How long does the job last? |
| salarymin | **Yes** | numeric Default: 0 | The minimum salary. |
| salarymax | **Yes** - must be equal to or greater than salary minimum | numeric Default: 0 | The maximum salary. |
| salaryper | **Yes** | Select List (values: annum, month, week, day, hour) | The pay cycle for the remuneration package. |
| salaryextras | No  | text | Extra benefits. |
| currency | **Yes** | Select List (obtain values using the [currencies/available](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/settings-management/custom-currencies.md) GET call) | The ISO-3 currency code. Use [custom-currencies](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/settings-management/custom-currencies.md) webservice to control and obtain the available ones. |
| jobtype | **Yes** | Select List: (values: 1=Contract, 2=Permanent, 4=Temporary) | Job type. |
| job\_time | **Yes** | Select List: (values: 1=Part-Time, 2=Full-Time) | Job Time. |
| category | **Yes** | [Get sector list values here](https://github.com/compono/idibu-api/blob/master/posting-api/Sector-and-locations.md#sectors) | Lookup for Sector - this should be a root sector from the sector list. |
| location | **Yes** | [Get location list values here](https://github.com/compono/idibu-api/blob/master/posting-api/Sector-and-locations.md#locations) | Lookup for Locations - this should be the two-letter country code from the location list. |
| sublocation | **Yes** | [Get location list values here](https://github.com/compono/idibu-api/blob/master/posting-api/Sector-and-locations.md#locations) | Lookup for Locations - this should be a child location from the location list. Only locations that belong under the country code specified in the `location` field will be accepted. |
| publish | No  | datetime YYYY-MM-DD HH:MM | You can queue a job to be sent out to the boards in the future, else it will be queued for immediate posting. Please mind this time has to be provided in GMT time zone. |

# Editable core fields

Some of the core fields (title, reference & description) are editable.

When marked as such in the request by using the `edit` parameter (check the examples) all the fields that are marked as 'editables' will have a corresponding text box or text area in the PCP, with the contents sent in the request, and the consultant can change this content prior to completing the post. Take into account that setting any of these fields to editable will force the PCP to always be returned.

# Sender fields

Please refer to [this article](https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/sender-tags.md) for more info.

# Dynamic core fields

Please refer to [this article](https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/dyn-vars.md) for more info

- - -

[Continue reading](https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/Sector-and-locations.md) to find out more about Sectors and Locations!
