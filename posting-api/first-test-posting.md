<p>You can use the XML below to provide a proof of concept post. To do this you&#39;ll need to:</p>

- Add these boards to your idibu account: 
  - a) idibu Developer Board (id 517)
  - b) Supply Chain Online (id 214)
  - c) Jobsite (id 41)
  - d) CV-Library (id 39) - just add test/test login credentials for the boards, if you do post adverts, they will fail to be accepted by the boards, though posts should work for our developer board.
- You will find an XML test page at <a href="http://www.idibu.com/get_xml_jobs.php" target="_blank">http://www.idibu.com/get_xml_jobs.php</a> - ensure it is in &#39;V3&#39; mode, add your HASH code and the XML to post into the system
- You will need to find the Team ID of your sender profile, check for the ID inside idibu when you hover over the Team to edit it
- The XML below posts to four boards - we have added extra fields for Supply Chain Online so you can see how you can optionally send this data through, or alternatively just let your advert posters complete these details on the posting completion page
- The redirect URL takes you to Google, this can of course be changed to whatever you want

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

## Common issues
<p>Q: I&#39;m getting errors like &quot;The DESCRIPTION tag is missing from the xml payload&quot;</p>
<p>A: Make sure you URL encode the XML payload rather than passing it as XML.</p>
<p>Q: I get a response the board &#39;x&#39; is not in our current subscribed list?</p>
<p>A: Make sure you have an active subscription to the board you are posting to. In your idibu account, go to job board subscriptions, inactive tab - and subscribe to the board you want to post to.</p>
<p>Q: Do I need to send the board login details in with the XML?</p>
<p>A: When you add a job board inside idibu you give the admin details there - when you post a job the system uses these fields to post the job to the board. You can optionally send these extra fields in the XML instead. If you do so they will override the board login details already loaded inside your account for that board.</p>

Be sure to check our [XML examples to help you developing](https://github.com/oneworldmarket/idibu-api/tree/master/api-v3/examples).

Before you begin coding, perhaps worth to check [our code library](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/code-library/.net-basic-interaction.md) in case there's something you can re-use and save time?

Good luck and happy postin!
