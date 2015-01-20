<h1>What is UPP?</h1>
<p>UPP stands for Uninersal Posting Page. Essentially it's all ready PHP page with idibu multiposting functionality giving you all the options you need to use with your system. All needed to be done here is to style up the page, so it looks like it was developed by you, but you can have posting working in your system withing minutes! We try to make it as easy and as functional as possible by including our <a href="http://support.idibu.com/default_import/Knowledgebase/Article/View/24/0/quotas-set-up---period-based">quota</a> and <a href="http://support.idibu.com/default_import/Knowledgebase/Article/View/15/0/force-posting">force posting</a> functionalities in the provided posting page.</p>
<h1>How to use it?</h1></p>
<p>Simply make a call to a link below with required paramaters. To make it super smooth you will need to map a few idibu parameters with your own vaiables.</p>
<h1>Posting URL</h1>
<p><br />All parameters can be provided in either a traditional HTTP GET or POST fashion and must be URL encoded. POST is recommended to get pass any character count limits typical for GET method. For example, in order to provide the hash, sender ID and job title into the system located at partners.idibu.com, you should use the following URL:</p>
<p><br /><a class="linkification-ext" title="Linkification: http://www.idibu.com/clients/upp/index.php?hash=yourhash&amp;senderId=123&amp;jobTitle=test%20title" href="http://www.idibu.com/clients/upp/index.php?hash=yourhash&senderId=123&jobTitle=test%20title">http://www.idibu.com/clients/upp/index.php?hash=yourhash&amp;senderId=123&amp;jobTitle=test%20title</a></p>
<h1>Styling</h1>
Here is how this can be looked when styling is applied:
<a href="http://www.idibu.com/clients/upp/index.php?hash=yourhash&senderId=123&jobTitle=test%20title&partnerId=bond">http://www.idibu.com/clients/upp/index.php?hash=yourhash&senderId=123&jobTitle=test%20title&partnerId=bond</a>
Just <a href="mailto:good@idibu.com">contact us</a> to become a partner and we'll help you getting this done.
<h1>Available parameters</h1></p>
<p><br />Here&rsquo;s the list of available parameters, their description and usage examples - - * denotes a parameter that is required.</p>
<p><br /><span style="font-size: large;">Account parameters:</span></p>
<ul>
<li>method - please specify as "post" if you are proving parameters using POST method. Otherwise GET will be accepted.</li>
<li>hash* - idibu account hash</li>
<li>partnerId - idibu partner ID, used for applying custom CSS and options on posting. Please contact us to obtain one.</li>
<li>Sender parameters:</li>
<li>senderId* &ndash; idibu user ID (can input sender's first name, last name and e-mail instead)</li>
</ul>
<p>OR (if senderId not provided)</p>
<ul>
<li>firstName* - sender's first name </li>
<li>lastName* - sender's last name</li>
<li>email* - sender's e-mail address</li>
<li><span class="wrapper"><span class="content"><span class="content_for_perma">phone* - sender's phone number<br /></span></span></span></li>
<li><span class="wrapper"><span class="content"><span class="content_for_perma">www* - sender's company www address</span></span></span></li>
<li><span class="wrapper"><span class="content"><span class="content_for_perma">country* - sender's country<br /></span></span></span></li>
<li><span class="wrapper"><span class="content"><span class="content_for_perma">postcode* - sender's post code<br /></span></span></span></li>
<li><span class="wrapper"><span class="content"><span class="content_for_perma">company* - sender's company name<br /></span></span></span></li>
</ul>
<p><br /><span style="font-size: large;">Job parameters:</span></p>
<ul>
<li>boards - list of board ID's to publish to, separated by commas (e.g. 37,151,123)</li>
<li>jobTitle - job title (e.g. A%20test%20title)</li>
<li>jobRef - job reference (e.g. REF123)</li>
<li>startDate &ndash; job start date in yyyy-mm-dd format with leading zeroes (e.g. 2013-06-25)</li>
<li>category - ID of selected category (available options listed below, e.g. 13)</li>
<li>location - ID of selected location (available options listed below, e.g. GB)</li>
<li>sublocation &ndash; sublocation&rsquo;s name (e.g. London)</li>
<li>sublocationId &ndash; sublocation&rsquo;s ID (e.g. 1024195)</li>
<li>mapPostCode &ndash; rather then provide an ID or text value of the location, you can provide a post code as a location source. idibu will use google location API to figure out the indended location based on it. By default we will try to map to UK post code, but if you will provide location variable (country code as above), we'll look for a location within the provided post code in the specified country.</li>
<li>term - employment term ID (available options listed below, e.g. 1)</li>
<li>duration - contract duration (only if employment term is set to "Contract" (ID: 1), e.g. Two%20months)</li>
<li>currency - salary currency ID (available options listed below, e.g. GBP)</li>
<li>minSalary - minimum salary (e.g. 2000)</li>
<li>maxSalary &ndash; maximum salary (e.g. 3000)</li>
<li>per - salary payment interval (e.g. month)</li>
<li>extraBenefits &ndash; extra benefits (e.g. premium%20health%20care)</li>
<li>salaryDescription &ndash; optional salary text override (e.g. 2000%20pounds%20or%20more)</li>
<li>appUrl &ndash; optional URL to use if one wants to apply for the job</li>
<li>jobDesc &ndash; job description (e.g. Here%20is%20a%20test%20description)</li>
</ul>
<p>&nbsp;</p>
<p><span style="font-size: large;">Config paramters:</span></p>
<ul>
<li>hideTitle - Set to true to hide job title field</li>
<li>hideRef - Set to true to hide job reference field</li>
<li>hideStartDate - Set to true to hide job start date field</li>
<li>hideAppUrl - Set to true to hide job application URL field</li>
<li>findUser - Set to true if you want to get a user ID by his e-mail from idibu</li>
<li>findJob - Set to false if you don't want to fetch job field values from old jobs based on reference</li>
<li>overrideRepost - Set to true if parameters from URL have higher priority than repost data (if findJob is set to true)</li>
<li>allowNewUsers - set to true if you like UPP to create a new idibu user if an unknown email appears in the email field. Set true as default.</li>
</ul>
<h1>Field values</h1><br />
<b>Category:</b><br /><br />
2 - Accountancy (Qualified)<br />
3 - Admin & Secretarial<br />
2778 - Advertising & PR<br />
2776 - Aerospace<br />
2780 - Agriculture Fishing & Forestry<br />
2782 - Arts<br />
4 - Automotive<br />
5 - Banking<br />
7 - Building & Construction<br />
8 - Call Centre & Customer Service<br />
6 - Charity & Voluntary<br />
2784 - Consultancy<br />
2786 - Defence & Military<br />
2788 - Design & Creative<br />
9 - Education & Training<br />
2790 - Electronics<br />
10 - Engineering<br />
2816 - Executive and Management<br />
2792 - Fashion<br />
11 - Financial Services<br />
12 - FMCG<br />
14 - Graduate Roles<br />
15 - Health & Safety<br />
16 - Hospitality & Catering<br />
17 - HR & Personnel<br />
13 - Insurance<br />
2802 - Internet & New Media<br />
18 - IT<br />
19 - Legal<br />
20 - Leisure & Sport<br />
2794 - Logistics Distribution & Supply Chain<br />
2808 - Manufacturing & Production<br />
21 - Marketing<br />
22 - Media<br />
2796 - Medical & Nursing<br />
2804 - Pharmaceuticals<br />
2806 - Property & Housing<br />
23 - Public Sector & Government<br />
24 - Purchasing & Procurement<br />
25 - Recruitment Consultancy<br />
26 - Retail<br />
27 - Sales<br />
28 - Science & Research<br />
29 - Social Care<br />
2798 - Telecommunications<br />
30 - Transport & Rail<br />
2810 - Travel & Tourism<br />
2812 - Utilities<br />
<br /><br />
Location:<br /><br />
GB - United Kingdom<br />
AD - Andorra<br />
AN - Angola<br />
AR - Argentina<br />
AU - Australia<br />
AT - Austria<br />
BB - Barbados<br />
BE - Belgium<br />
BR - Brazil<br />
BG - Bulgaria<br />
CA - Canada<br />
GG - Channel Islands<br />
CN - China<br />
HR - Croatia<br />
DM - Denmark<br />
EG - Egypt<br />
FO - Faroe Islands<br />
FR - France<br />
DE - Germany<br />
GP - Guadeloupe<br />
GU - Guam<br />
HG - Hong Kong<br />
IN - India<br />
ID - Indonesia<br />
IE - Ireland<br />
IM - Isle of Man<br />
IT - Italy<br />
JP - Japan<br />
JE - Jersey<br />
LI - Liechtenstein<br />
LU - Luxembourg<br />
MK - Macedonia<br />
MY - Malaysia<br />
MA - Malta<br />
MH - Marshall Islands<br />
MQ - Martinique<br />
YT - Mayotte<br />
MX - Mexico<br />
MD - Moldova<br />
MC - Monaco<br />
NL - Netherlands<br />
NZ - New Zealand<br />
MP - Northern Mariana Islands<br />
NO - Norway<br />
PK - Pakistan<br />
PL - Poland<br />
PT - Portugal<br />
PR - Puerto Rico<br />
QA - Qatar<br />
SM - San Marino<br />
SI - Singapore<br />
ZA - South Africa<br />
ES - Spain<br />
LK - Sri Lanka<br />
PM - St. Pierre and Miquelon<br />
CH - Switzerland<br />
TH - Thailand<br />
TR - Turkey<br />
UE - United Arab Emirates<br />
US - United States<br />
VA - Vatican City (Holy See)<br />
VI - Virgin Islands (U.S.)<br />
ZZ - Rest of the World<br />
<br /><br />
Employment term:<br />
2 – Permanent<br />
1 – Contract<br />
4 – Temporary<br />
<br />
Salaries:<br /><br />
USD - US Dollars <br />
($) EU – Euro<br />
(€) GBP – British Pound<br />
<br /><br />
Working hours:<br /><br />
2 – Full-time<br />
1 – Part-time<br />
<br />
Salary payment interval (per):<br /><br />
annum – Annum<br />
month – Month<br />
week – Week<br />
day – Day<br />
hour - Hour<br />
