<h1>What is UPP?</h1>
<p>UPP stands for Uninersal Posting Page. Essentially it's all ready PHP page with idibu multiposting functionality giving you all the options you need to use with your system. All needed to be done here is to style up the page, so it looks like it was developed by you, but you can have posting working in your system withing minutes!</p>
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
<h1>Field values</h1>
<b>Category:</b>
2 - Accountancy (Qualified)
3 - Admin & Secretarial
2778 - Advertising & PR
2776 - Aerospace
2780 - Agriculture Fishing & Forestry
2782 - Arts
4 - Automotive
5 - Banking
7 - Building & Construction
8 - Call Centre & Customer Service
6 - Charity & Voluntary
2784 - Consultancy
2786 - Defence & Military
2788 - Design & Creative
9 - Education & Training
2790 - Electronics
10 - Engineering
2816 - Executive and Management
2792 - Fashion
11 - Financial Services
12 - FMCG
14 - Graduate Roles
15 - Health & Safety
16 - Hospitality & Catering
17 - HR & Personnel
13 - Insurance
2802 - Internet & New Media
18 - IT
19 - Legal
20 - Leisure & Sport
2794 - Logistics Distribution & Supply Chain
2808 - Manufacturing & Production
21 - Marketing
22 - Media
2796 - Medical & Nursing
2804 - Pharmaceuticals
2806 - Property & Housing
23 - Public Sector & Government
24 - Purchasing & Procurement
25 - Recruitment Consultancy
26 - Retail
27 - Sales
28 - Science & Research
29 - Social Care
2798 - Telecommunications
30 - Transport & Rail
2810 - Travel & Tourism
2812 - Utilities

Location:
GB - United Kingdom
AD - Andorra
AN - Angola
AR - Argentina
AU - Australia
AT - Austria
BB - Barbados
BE - Belgium
BR - Brazil
BG - Bulgaria
CA - Canada
GG - Channel Islands
CN - China
HR - Croatia
DM - Denmark
EG - Egypt
FO - Faroe Islands
FR - France
DE - Germany
GP - Guadeloupe
GU - Guam
HG - Hong Kong
IN - India
ID - Indonesia
IE - Ireland
IM - Isle of Man
IT - Italy
JP - Japan
JE - Jersey
LI - Liechtenstein
LU - Luxembourg
MK - Macedonia
MY - Malaysia
MA - Malta
MH - Marshall Islands
MQ - Martinique
YT - Mayotte
MX - Mexico
MD - Moldova
MC - Monaco
NL - Netherlands
NZ - New Zealand
MP - Northern Mariana Islands
NO - Norway
PK - Pakistan
PL - Poland
PT - Portugal
PR - Puerto Rico
QA - Qatar
SM - San Marino
SI - Singapore
ZA - South Africa
ES - Spain
LK - Sri Lanka
PM - St. Pierre and Miquelon
CH - Switzerland
TH - Thailand
TR - Turkey
UE - United Arab Emirates
US - United States
VA - Vatican City (Holy See)
VI - Virgin Islands (U.S.)
ZZ - Rest of the World

Employment term:
2 – Permanent
1 – Contract
4 – Temporary

Salaries:
USD - US Dollars 
($) EU – Euro
(€) GBP – British Pound

Working hours:
2 – Full-time
1 – Part-time

Salary payment interval (per):
annum – Annum
month – Month
week – Week
day – Day
hour - Hour
