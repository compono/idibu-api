<h1>
	Sectors</h1>
<p>The sectors for idibu are fixed to this current list - <a href="/attachments/idibu_sector_list.xls">download the idibu sector list in XLS format</a>.</p>
<h1>
	Locations</h1>
<p>idibu now has a global location system which means the amount of location possibilities are huge.</p>
<p>This is a method to call details on specific location. The data returned can be fed up to idibu&#39;s posting API v3, to identify the proper location you wish to post to.</p>
<h1>
	<strong>Parameters</strong></h1>
<p>filter_name - Name or part of the of the location you are looking for<br />
	count - maximal number of results</p>
<h1>
	<strong>Considerations</strong></h1>
<p>When building code that will call location webservice, please take into account the following:<br />
	<br />
	- Your location program should call the webservice with a location string and return a list of locations to choose from before posting. <strong>The country code will be your location id </strong>and <strong>the id returned by the web-service should be used as sublocation id</strong>. The list of county codes can be found below.<br />
	- One location can have duplicate entries in the same county/state due to different post codes. It is worth to display only one entry for specific county/state<br />
	- To correctly identify duplicates that are different locations (towns) please take the state/county tag for consideration. County tag can be found in UK and Ireland, while state is an additional tag for USA.<br />
	- Some locations may have up to 15 legitimate duplicates all over the country. Make sure your program is ready for that.</p>
<h1>
	<strong>Country codes</strong></h1>
<p>To make a correct call, you will have to call a location within a country represented by one of the following country codes: <code>
GB - United Kingdom
US - United States
AD - Andorra
AN - Angola
AR - Argentina
AT - Austria
AU - Australia
BB - Barbados
BE - Belgium
BG - Bulgaria
BR - Brazil
CA - Canada
CH - Switzerland
CN - China
DE - Germany
DM - Denmark
EG - Egypt
ES - Spain
FO - Faroe Islands
FR - France
GG - Channel Islands
GP - Guadeloupe
GU - Guam
HG - Hong Kong
HR - Croatia
ID - Indonesia
IE - Ireland
IM - Isle of Man
IN - India
IT - Italy
JE - Jersey
JP - Japan
LI - Liechtenstein
LK - Sri Lanka
LU - Luxembourg
MA - Malta
MC - Monaco
MD - Moldova
MH - Marshall Islands
MK - Macedonia
MP - Northern Mariana Islands
MQ - Martinique
MX - Mexico
MY - Malaysia
NL - Netherlands
NO - Norway
NZ - New Zealand
PK - Pakistan
PM - St. Pierre and Miquelon
PR - Puerto Rico
PT - Portugal
QA - Qatar
SI - Singapore
SM - San Marino
TH - Thailand
TR - Turkey
UE - United Arab Emirates
VA - Vatican City
VI - Virgin Islands (U.S.)
YT - Mayotte
ZA - South Africa
ZZ - Rest of the wold (Other countries)
</code></p>
<h2>
	<strong>Request</strong></h2>
<pre>
<code>
POST http://ws.idibu.com/ws/rest/v1/locations/<COUNTRY CODE HERE>/find?hash=<CLIENT HASH HERE>&filter_name=<LOCATION STRING YOU ARE LOOKING FOR>&count=<MAXIMAL NUMBER OF RESULTS>
</code>


</pre>
<h2>
	Response</h2>
<pre>
<code type="xml">
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
&lt;response&gt;
&lt;locations&gt;
&nbsp;&lt;location&gt;
&nbsp;&nbsp;&nbsp;&lt;id&gt;1024195&lt;/id&gt;
&nbsp;&nbsp;&nbsp;&lt;place_name&gt;London&lt;/place_name&gt;
&nbsp;&nbsp;&nbsp;&lt;country_code&gt;GB&lt;/country_code&gt;
&nbsp;&nbsp;&nbsp;&lt;postal_code&gt;EC1A&lt;/postal_code&gt;
&nbsp;&nbsp;&nbsp;&lt;latitude&gt;51.51&lt;/latitude&gt;
&nbsp;&nbsp;&nbsp;&lt;longitude&gt;-0.13&lt;/longitude&gt;
&nbsp;&nbsp;&nbsp;&lt;county&gt;Greater London&lt;/county&gt;
&nbsp;&nbsp;&nbsp;&lt;region&gt;SouthEast&lt;/region&gt;
&nbsp;&nbsp;&nbsp;&lt;country&gt;England&lt;/country&gt;
&nbsp;&lt;/location&gt;
&lt;/locations&gt;
&lt;/response&gt;

&lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code>
</pre>
<p>Alternately, you can use a fixed list for few countries we have prepared, like below:</p>
<ul>
	<li>
		<a href="/attachments/GB.rar">United Kingdom (GB)</a></li>
	<li>
		<a href="/attachments/AU.rar">Australia (AU)</a></li>
</ul>
<p>You can also use our old legacy location list which has a thorough UK breakdown, and reasonable global coverage. However we recommend to use the options above.</p>
<p>To get a list of these locations then please use the discovery service:</p>
<pre>
<code>
http://ws.idibu.com/clients/api/enum.php?enum=Location&source=idibu&hash=[INSERT HASH VALUE HERE]
</code></pre>
