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
GB - United Kingdom<br />
US - United States<br />
AD - Andorra<br />
AN - Angola<br />
AR - Argentina<br />
AT - Austria<br />
AU - Australia<br />
BB - Barbados<br />
BE - Belgium<br />
BG - Bulgaria<br />
BR - Brazil<br />
CA - Canada<br />
CH - Switzerland<br />
CN - China<br />
DE - Germany<br />
DM - Denmark<br />
EG - Egypt<br />
ES - Spain<br />
FO - Faroe Islands<br />
FR - France<br />
GG - Channel Islands<br />
GP - Guadeloupe<br />
GU - Guam<br />
HG - Hong Kong<br />
HR - Croatia<br />
ID - Indonesia<br />
IE - Ireland<br />
IM - Isle of Man<br />
IN - India<br />
IT - Italy<br />
JE - Jersey<br />
JP - Japan<br />
LI - Liechtenstein<br />
LK - Sri Lanka<br />
LU - Luxembourg<br />
MA - Malta<br />
MC - Monaco<br />
MD - Moldova<br />
MH - Marshall Islands<br />
MK - Macedonia<br />
MP - Northern Mariana Islands<br />
MQ - Martinique<br />
MX - Mexico<br />
MY - Malaysia<br />
NL - Netherlands<br />
NO - Norway<br />
NZ - New Zealand<br />
PK - Pakistan<br />
PM - St. Pierre and Miquelon<br />
PR - Puerto Rico<br />
PT - Portugal<br />
QA - Qatar<br />
SI - Singapore<br />
SM - San Marino<br />
TH - Thailand<br />
TR - Turkey<br />
UE - United Arab Emirates<br />
VA - Vatican City<br />
VI - Virgin Islands (U.S.)<br />
YT - Mayotte<br />
ZA - South Africa<br />
ZZ - Rest of the wold (Other countries)<br />
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
