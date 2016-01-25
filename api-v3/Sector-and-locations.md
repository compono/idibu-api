<h1>
	Sectors</h1>
<p>The sectors for idibu are fixed to this current list - <a href="http://www.idibu.com/images/stories/Portal_logos/idibu_sector_list.xls">download the idibu sector list in XLS format</a>.</p>
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
	- Some locations may have up to 15 legitimate duplicates all over the country. Make sure your program is ready for that.<br />
	- We suggest you build a location look-up field in your application that emulates idibu's behaviour: <br><br>
<img src = "http://www.idibu.com/images/stories/Portal_logos/lookup_graphic.png" /><br /><br />
The top dropdown is a static country list, whereas the other field is a look-up field that queries idibu location API after each typed in letter.</p><br /><br />
<h1>
	<strong>Country codes</strong></h1>
<h3>To make a correct call, you will have to call a location within a country represented by one of the following country codes:</h3>

| code | Country name |
|---|---|
| GB | United Kingdom |
| GB | United Kingdom |
| US | United States |
| US | United States |
| AD | Andorra |
| AD | Andorra |
| AN | Angola |
| AN | Angola |
| AR | Argentina |
| AR | Argentina |
| AT | Austria |
| AT | Austria |
| AU | Australia |
| AU | Australia |
| BB | Barbados |
| BB | Barbados |
| BE | Belgium |
| BE | Belgium |
| BG | Bulgaria |
| BG | Bulgaria |
| BR | Brazil |
| BR | Brazil |
| CA | Canada |
| CA | Canada |
| CH | Switzerland |
| CH | Switzerland |
| CN | China |
| CN | China |
| DE | Germany |
| DE | Germany |
| DM | Denmark |
| DM | Denmark |
| EG | Egypt |
| EG | Egypt |
| ES | Spain |
| ES | Spain |
| FO | Faroe Islands |
| FO | Faroe Islands |
| FR | France |
| FR | France |
| GG | Channel Islands |
| GG | Channel Islands |
| GP | Guadeloupe |
| GP | Guadeloupe |
| GU | Guam |
| GU | Guam |
| HG | Hong Kong |
| HG | Hong Kong |
| HR | Croatia |
| HR | Croatia |
| ID | Indonesia |
| ID | Indonesia |
| IE | Ireland |
| IE | Ireland |
| IM | Isle of Man |
| IM | Isle of Man |
| IN | India |
| IN | India |
| IT | Italy |
| IT | Italy |
| JE | Jersey |
| JE | Jersey |
| JP | Japan |
| JP | Japan |
| LI | Liechtenstein |
| LI | Liechtenstein |
| LK | Sri Lanka |
| LK | Sri Lanka |
| LU | Luxembourg |
| LU | Luxembourg |
| MA | Malta |
| MA | Malta |
| MC | Monaco |
| MC | Monaco |
| MD | Moldova |
| MH | Marshall Islands |
| MK | Macedonia |
| MP | Northern Mariana Islands |
| MQ | Martinique |
| MX | Mexico |
| MY | Malaysia |
| NL | Netherlands |
| NO | Norway |
| NZ | New Zealand |
| PK | Pakistan |
| PM | St. Pierre and Miquelon |
| PR | Puerto Rico |
| PT | Portugal |
| QA | Qatar |
| SI | Singapore |
| SM | San Marino |
| TH | Thailand |
| TR | Turkey |
| UE | United Arab Emirates |
| VA | Vatican City |
| VI | Virgin Islands (U.S.) |
| YT | Mayotte |
| ZA | South Africa |
| ZZ | Rest of the wold (Other countries) |

<h2><strong>Request</strong></h2>

```
POST http://ws.idibu.com/ws/rest/v1/locations/<COUNTRY CODE HERE>/find?hash=<CLIENT HASH HERE>&filter_name=<LOCATION STRING YOU ARE LOOKING FOR>&count=<MAXIMAL NUMBER OF RESULTS>
```

<h3><strong>Example</strong></h3>
```
POST http://ws.idibu.com/ws/rest/v1/locations/GB/find?hash=<CLIENT HASH HERE>&filter_name=london&count=1
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

Worst case scenario, you can use a fixed list locations for specific country. We have prepared list for:<br />
<br />
<a href = "http://www.idibu.com/images/stories/Portal_logos/GB.rar">UK - United Kingdom</a><br />
<a href = "http://www.idibu.com/images/stories/Portal_logos/AU.rar">AU - Australia</a><br />
<br />
that should speed up your developement, but we stress that dynamic location webservice usage is the best way to go!
<br /><br />
<a href="https://github.com/oneworldmarket/idibu-api/blob/master/api-v3/spec-data.md"> Click here to find about board specific tags</a>
