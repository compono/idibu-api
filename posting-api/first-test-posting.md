## Test Post Example and Common Issues

To perform a preliminary test posting, you can utilise the provided XML below as a proof of concept. The process involves the following steps:

1. Add the specified boards to your idibu account: <br> <br>
   a) idibu Developer Board (ID 517) <br>
   b) Supply Chain Online (ID 214) <br>
   c) Jobsite (ID 41) <br>
   d) CV-Library (ID 39)

   If you intend to post jobs, simply use test/test login credentials. Please note, actual advert postings to these boards will **not** be accepted or published; however, they should function with our developer board.

2. Access the XML test page at http://www.idibu.com/get_xml_jobs.php. Ensure it's set to 'V3' mode, insert your account HASH key and XML for posting into the system.


The provided XML is configured to post to four boards. Notably, extra fields have been included for Supply Chain Online, showcasing how you can optionally transmit this data. Alternatively, you can allow advert posters to complete these details using the [Post Completion Page](https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/pcp.md)

The redirection URL leads to Google, which can be customised to your preference.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<idibu>
  <method>add</method>
  <config>
    <show_durations>no</show_durations>
    <completionurl>email</completionurl>
    <advertcompletionemail>bob@bob.com</advertcompletionemail>
    <lockboards>yes</lockboards>
    <redirecturl>http://www.google.com
    </redirecturl>
    <validate_level>warning</validate_level>
  </config>
  <job>
    <title>
      <![CDATA[Account Manager - Technical Sourcing]]>
    </title>
    <reference>ABC123456789</reference>
    <description>
      <![CDATA[Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus quis metus in felis tincidunt ullamcorper quis at ante. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nam ultrices mattis tortor, eget cursus tellus placerat at.]]>
    </description>
    <sender>
      <team id="33000169"/>
      <name>Steve</name>
      <lastname>Rogers</lastname>
      <email>test@mail.net</email>
      <company>One World Market</company>
      <phone>+44 (0) 111-1111111</phone>
      <www>http://uk.idibu.com
      </www>
      <country>UK</country>
      <postcode>020 1111 1111</postcode>
    </sender>
    <category id="21"/>
    <location id="8"/>
    <sublocation id="668"/>
    <jobtype id="2"/>
    <startdate>2010-11-26</startdate>
    <duration>Full time</duration>
    <salarymin>20000</salarymin>
    <salarymax>25000</salarymax>
    <salaryper value="annum"/>
    <currency>GBP</currency>
    <publish>2010-11-26</publish>
    <posts>
      <board id="214">
        <duration days="21"/>
        <extrafield name="sco_sector"><item id="15"/></extrafield>
        <extrafield name="sco_featured"><item id="no"/></extrafield>
        <extrafield name="sco_location" parent="82">
          <!-- double select -->
          <item id="85"/>
        </extrafield>
        <extrafield name="sco_summary">testing text for text area<!-- text area --></extrafield>
        <extrafield name="sco_locover">London</extrafield>
        <extrafield name="cso_osal">No benefits</extrafield>
      </board>
      <board id="517">
        <duration days="7"/>
        <extrafield name="idibudts_cat">1</extrafield>
      </board>
      <board id="41">
        <duration days="1"/>
      </board>
      <board id="39">
        <duration days="7"/>
      </board>
    </posts>
  </job>
</idibu>
```

Should you encounter any issues during this process, some common queries and resolutions are provided below:

## Troubleshooting and Common Queries

Encountering any issues during this process? Below are some common queries and their resolutions:

**Q: I'm encountering errors like "The DESCRIPTION tag is missing from the XML payload."**

A: To address this, ensure that you URL encode the XML payload rather than passing it as plain XML.

**Q: I receive a response stating that board 'x' is not in our current subscribed list?**

A: To resolve this, verify that you have an active subscription in the idibu instance you're using for the board you're attempting to post to. 

**Q: Is it necessary to include the board login details in the XML?**

A: When you add a job board within idibu, in nearly all cases you will need to provide posting credntials. During the job posting process, the system uses these details by default when posting to the respective job board(s). Optionally, you can incorporate these extra fields within the XML. This will override the board login details already present in your account for that specific board.

---


Before commencing your coding [consider exploring our XML examples for guidance](https://github.com/oneworldmarket/idibu-api/tree/master/posting-api/examples). Also [our code library](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/code-library/.net-basic-interaction.md) library might also offer reusable components that can expedite your development process.
