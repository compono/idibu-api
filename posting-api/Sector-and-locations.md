<h1>Sectors</h1>
<p>The sectors for idibu are fixed to this current list:</p>
<table>
<thead><tr><th>ID</th><th>Sector</th></tr></thead>
<tbody>
<tr><td>1</td><td>Accountancy</td></tr>
<tr><td>2</td><td>Accountancy (Qualified)</td></tr>
<tr><td>3</td><td>Admin & Secretarial</td></tr>
<tr><td>2778</td><td>Advertising & PR</td></tr>
<tr><td>2776</td><td>Aerospace</td></tr>
<tr><td>2780</td><td>Agriculture Fishing & Forestry</td></tr>
<tr><td>2782</td><td>Arts</td></tr>
<tr><td>4</td><td>Automotive</td></tr>
<tr><td>5</td><td>Banking</td></tr>
<tr><td>7</td><td>Building & Construction</td></tr>
<tr><td>8</td><td>Call Centre & Customer Service</td></tr>
<tr><td>6</td><td>Charity & Voluntary</td></tr>
<tr><td>2784</td><td>Consultancy</td></tr>
<tr><td>2786</td><td>Defence & Military</td></tr>
<tr><td>2788</td><td>Design & Creative</td></tr>
<tr><td>9</td><td>Education & Training</td></tr>
<tr><td>2790</td><td>Electronics</td></tr>
<tr><td>10</td><td>Engineering</td></tr>
<tr><td>2816</td><td>Executive and Management</td></tr>
<tr><td>2792</td><td>Fashion</td></tr>
<tr><td>11</td><td>Financial Services</td></tr>
<tr><td>12</td><td>FMCG</td></tr>
<tr><td>14</td><td>Graduate Roles</td></tr>
<tr><td>15</td><td>Health & Safety</td></tr>
<tr><td>16</td><td>Hospitality & Catering</td></tr>
<tr><td>17</td><td>HR & Personnel</td></tr>
<tr><td>13</td><td>Insurance</td></tr>
<tr><td>2802</td><td>Internet & New Media</td></tr>
<tr><td>18</td><td>IT</td></tr>
<tr><td>19</td><td>Legal</td></tr>
<tr><td>20</td><td>Leisure & Sport</td></tr>
<tr><td>2794</td><td>Logistics Distribution & Supply Chain</td></tr>
<tr><td>2808</td><td>Manufacturing & Production</td></tr>
<tr><td>21</td><td>Marketing</td></tr>
<tr><td>22</td><td>Media</td></tr>
<tr><td>2796</td><td>Medical & Nursing</td></tr>
<tr><td>31</td><td>Other</td></tr>
<tr><td>2804</td><td>Pharmaceuticals</td></tr>
<tr><td>2806</td><td>Property & Housing</td></tr>
<tr><td>23</td><td>Public Sector & Government</td></tr>
<tr><td>24</td><td>Purchasing & Procurement</td></tr>
<tr><td>25</td><td>Recruitment Consultancy</td></tr>
<tr><td>26</td><td>Retail</td></tr>
<tr><td>27</td><td>Sales</td></tr>
<tr><td>28</td><td>Science & Research</td></tr>
<tr><td>29</td><td>Social Care</td></tr>
<tr><td>2798</td><td>Telecommunications</td></tr>
<tr><td>30</td><td>Transport & Rail</td></tr>
<tr><td>2810</td><td>Travel & Tourism</td></tr>
<tr><td>2812</td><td>Utilities</td></tr>
</tbody></table>
<p><a href="http://www.idibu.com/clients/api/idibu_sector_list.xls">Download the idibu sector list in XLS format</a>.</p>
<h1>Locations</h1>
<p>idibu now has a global location system which means the amount of location possibilities are huge.</p>
<p>This is a method to call details on specific location. The data returned can be fed up to idibu&#39;s posting API, to identify the proper location you wish to post to.</p>
<h1>
	<strong>Parameters</strong></h1>
<p><code>filter_name</code> - Name or part of the name of the location you are looking for. This will search for the <code>place_name</code> and <code>postal_code</code> (see the example response below).<br />
<code>count</code> - Maximum number of results.</p>
<h1>
	<strong>Considerations</strong></h1>
<p>When building code that will call location webservice, please take into account the following:<br />
	<br />
	- Your software should call the webservice with a location string and return a list of locations to choose from before posting. <strong>The country code will be your location id</strong> and <strong>the id returned by the web-service should be used as sublocation id</strong>. The list of county codes can be found below.<br />
	- One location can have duplicate entries in the same county/state due to different post codes.<br />
	- To correctly identify duplicates that are different locations (towns), please take the state/county tag into consideration. County tag can be found in UK and Ireland, while state is an additional tag for USA.<br />
	- Some locations may have up to 15 legitimate duplicates all over the country. Make sure your software is ready to handle that.<br />
	- We suggest you build a location look-up field in your application that emulates idibu's behaviour: <br><br>
<img src = "http://www.idibu.com/images/stories/Portal_logos/lookup_graphic.png" /><br /><br />
The top dropdown is a static country list, whereas the other field is a look-up field that queries idibu location API as the text is typed in.</p>
<h1><strong>Country codes</strong></h1>
<p>To make a correct call, you will have to call a location within a country represented by one of the following country codes:</p>

| code | Country name |
|---|---|
| AD | Andorra |
| AN | Angola |
| AR | Argentina |
| AU | Australia |
| AT | Austria |
| BD | Bangladesh |
| BB | Barbados |
| BE | Belgium |
| BM | Bermuda |
| BR | Brazil |
| BN | Brunei |
| BG | Bulgaria |
| CA | Canada |
| GG | Channel Islands |
| CN | China |
| CO | Colombia |
| HR | Croatia |
| CZ | Czech Republic |
| DM | Denmark |
| EG | Egypt |
| GQ | Equatorial Guinea |
| FO | Faroe Islands |
| FR | France |
| GA | Gabon |
| DE | Germany |
| GH | Ghana |
| GR | Greece |
| GP | Guadeloupe |
| GU | Guam |
| HK | Hong Kong |
| HU | Hungary |
| IN | India |
| ID | Indonesia |
| IQ | Iraq |
| IE | Ireland |
| IM | Isle of Man |
| IT | Italy |
| JP | Japan |
| JE | Jersey |
| JO | Jordan |
| LY | Libya |
| LI | Liechtenstein |
| LU | Luxembourg |
| MK | Macedonia |
| MY | Malaysia |
| MA | Malta |
| MH | Marshall Islands |
| MQ | Martinique |
| YT | Mayotte |
| MX | Mexico |
| MD | Moldova |
| MC | Monaco |
| MZ | Mozambique |
| MM | Myanmar |
| NA | Namibia |
| NL | Netherlands |
| NZ | New Zealand |
| NG | Nigeria |
| MP | Northern Mariana Islands |
| NO | Norway |
| OM | Oman |
| PK | Pakistan |
| PE | Peru |
| PL | Poland |
| PT | Portugal |
| PR | Puerto Rico |
| QA | Qatar |
| RE | Reunion |
| RO | Romania |
| RU | Russia |
| SM | San Marino |
| SA | Saudi Arabia |
| RU | Serbia |
| SI | Singapore |
| ZA | South Africa |
| KR | South Korea |
| ES | Spain |
| LK | Sri Lanka |
| PM | St. Pierre and Miquelon |
| SE | Sweden |
| CH | Switzerland |
| TW | Taiwan |
| TZ | Tanzania |
| TH | Thailand |
| TN | Tunisia |
| TR | Turkey |
| UE | United Arab Emirates |
| GB | United Kingdom |
| US | United States |
| VA | Vatican City (Holy See) |
| VE | Venezuela |
| VN | Vietnam |
| VI | Virgin Islands (U.S.) |
| ZZ | Rest of the world (other countries) |

<h2><strong>Request</strong></h2>

```
GET http://ws.idibu.com/ws/rest/v1/locations/<COUNTRY CODE HERE>/find?hash=<CLIENT HASH HERE>&filter_name=<LOCATION STRING YOU ARE LOOKING FOR>&count=<MAXIMUM NUMBER OF RESULTS>
```

<h3><strong>Example</strong></h3>

```
GET http://ws.idibu.com/ws/rest/v1/locations/GB/find?hash=<CLIENT HASH HERE>&filter_name=london&count=1
```

<h2>Response</h2>

```xml
<idibu generator="idibu" version="1.0">
<response>
<locations>
 <location>
   <id>1024195</id>
   <place_name>London</place_name>
   <country_code>GB</country_code>
   <postal_code>EC1A</postal_code>
   <latitude>51.51</latitude>
   <longitude>-0.13</longitude>
   <county>Greater London</county>
   <region>SouthEast</region>
   <country>England</country>
 </location>
</locations>
</response>

<status>success</status>
</idibu>
```
<a href="https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/spec-data.md">Click here to explore board specific tags</a>
