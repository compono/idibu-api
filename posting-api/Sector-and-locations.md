## Sectors
The idibu platform classifies job postings into sectors encompassing various industries and fields. This list provides a clear overview of the available sectors:

| ID   | Sector                            |
| ---- | --------------------------------- |
| 1    | Accountancy                       |
| 2    | Accountancy (Qualified)           |
| 3    | Admin & Secretarial               |
| 2778 | Advertising & PR                  |
| 2776 | Aerospace                         |
| 2780 | Agriculture Fishing & Forestry    |
| 2782 | Arts                              |
| 4    | Automotive                        |
| 5    | Banking                           |
| 7    | Building & Construction           |
| 8    | Call Centre & Customer Service    |
| 6    | Charity & Voluntary               |
| 2784 | Consultancy                       |
| 2786 | Defence & Military                |
| 2788 | Design & Creative                 |
| 9    | Education & Training              |
| 2790 | Electronics                       |
| 2818 | Energy & Renewables               |
| 10   | Engineering                       |
| 2816 | Executive & Management            |
| 2792 | Fashion                           |
| 11   | Financial Services                |
| 12   | FMCG                              |
| 14   | Graduate Roles                    |
| 15   | Health & Safety                   |
| 16   | Hospitality & Catering            |
| 17   | HR & Personnel                    |
| 13   | Insurance                         |
| 2802 | Internet & New Media              |
| 18   | IT                                |
| 19   | Legal                             |
| 20   | Leisure & Sport                   |
| 2794 | Logistics Distribution & Supply Chain |
| 2808 | Manufacturing & Production        |
| 21   | Marketing                         |
| 22   | Media                             |
| 2796 | Medical & Nursing                 |
| 31   | Other                             |
| 2804 | Pharmaceuticals                   |
| 2806 | Property & Housing                |
| 23   | Public Sector & Government        |
| 24   | Purchasing & Procurement          |
| 25   | Recruitment Consultancy           |
| 26   | Retail                            |
| 27   | Sales                             |
| 28   | Science & Research                |
| 29   | Social Care                       |
| 2798 | Telecommunications                |
| 30   | Transport & Rail                  |
| 2810 | Travel & Tourism                  |
| 2812 | Utilities                         |

[Download the idibu sector list in XLS format](https://www.idibu.com/clients/api/idibu_sector_list.xls).

---

## Locations
The idibu platform has introduced a robust global location system, offering an extensive range of potential job posting locations. This system facilitates the retrieval of specific location details, which can be seamlessly integrated with idibu's posting API to identify the desired job posting location precisely.

### Endpoint
#### `https://ws.idibu.com/ws/rest/v1/locations/`

### Available methods
#### `GET /[country]/find`
Returns all matching locations for a given 2-letter ISO `[country]` code.

[See below](https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/Sector-and-locations.md#country-codes) for the available list of countries.

#### Query parameters
Parameter Name | Type restrictions | Required? | Notes
-- | -- | -- | --
`hash` | **String** | **Yes** | Hash of the idibu account to which the request pertains.
`filter_name` | **String** | **Yes** | A full or partial location name for searching. This query will encompass both the place name and postal code.
`count` | **Integer**<br/><br/>Min: 1<br/>Max: 100<br/>Default: 10 | No | Number of matching locations to return.

#### Response format

```xml
<idibu generator="idibu" version="1.0">
  <response>
    <locations>
      <location>
        <id>[integer]</id> <!-- sublocation id -->
        <place_name>[string]</place_name> <!-- location name -->
        <country_code>[string]</country_code> <!-- 2-letter ISO code -->
        <postal_code>[string]</postal_code> <!-- postal code -->
        <latitude>[double]</latitude> <!-- latitude; might be approximate or not present, especially for bigger cities or areas -->
        <longitude>[double]</longitude> <!-- longitude; might be approximate or not present, especially for bigger cities or areas -->
        <county>[string]</county> <!-- county or state under which the location belongs; might be empty for some locations -->
        <region>[string]</region> <!-- region under which the location belongs; might be empty for some locations -->
        <country>[string]</country> <!-- country name -->
      </location>
    </locations>
  </response>
  <status>["success"|"failed"]</status> <!-- whether the request succeeded or not -->
</idibu>
```

### Considerations
When developing code to leverage the location webservice, keep the following key points in mind:
- Your software should utilise the webservice to fetch a list of potential locations based on the provided location string. This list can then be presented for selection in your platform prior to the job posting.
- The country code will function as the location identifier, while the ID returned by the webservice should serve as the sublocation ID.
- To account for varying postal codes, remember that a single location might have multiple entries within the same county or state. To distinguish these instances, incorporate the state/county tag, applicable to the UK, Ireland, and the USA.
- Certain locations could have multiple legitimate duplicates throughout the country, sometimes up to 15 instances, usually varying by postal code. Ensure your software can accommodate such scenarios.
- Consider implementing a location look-up field in your application that mirrors idibu's functionality:

![location lookup](https://www.idibu.com/images/stories/Portal_logos/lookup_graphic.png)

The upper dropdown offers a fixed list of countries, while the subsequent field dynamically queries idibu's location API as the text is entered.

### Country Codes
For accurate calls, use one of the following country codes to specify the country:

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
| JD | Jordan |
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
| PH | Philippines |
| PL | Poland |
| PT | Portugal |
| PR | Puerto Rico |
| QA | Qatar |
| RE | Reunion |
| RO | Romania |
| RU | Russia |
| SM | San Marino |
| SA | Saudi Arabia |
| RS | Serbia |
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

[Click here to explore board specific tags](https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/spec-data.md)
