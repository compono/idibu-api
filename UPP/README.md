## What is UPP?
UPP stands for Universal Posting Page. Essentially it's a ready-to-go page that provides you with all the tools you need to add idibu's posting engine to your own platform. All you need to do here is to style the page, but you can have posting working in your system within minutes!

Once the UPP form is all filled and sent, the user will be asked to complete the posting by providing fields specific to chosen boards using the [Post Completion Page](https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/pcp.md).

## How to use it?
Simply make a call to the link below with required parameters. To make it super smooth, it is best to map idibu parameters with your own variables.

## Posting URL
All parameters can be provided in either a traditional HTTP GET or POST fashion, and must be URL-encoded. POST is recommended to get past any character count limits typical for the GET method. For example, in order to provide the hash, sender ID, and job title when generating the page, you should use the following URL:

https://www.idibu.com/clients/upp/index.php?hash=YOUR_HASH&email=SENDER_EMAIL&jobTitle=test%20title

In theory, with the link above, you could have an almost _instant_ integration with little development work. Once that is live, you'd just need to work on styling and parameter mapping, and you will have a fully functioning multiposting system in your ATS!

## Styling
Here is how this can look/could look when styling is applied:

![image](https://www.evernote.com/shard/s383/sh/282b25e9-2780-49ea-acf7-7575a496a640/1cc19af67c2f681f365f633470598ac8/res/5ba5bfaa-a032-4a40-b5aa-77ca48aa5a5e/skitch.png)

Just [contact us](mailto:good@idibu.com) to become a partner and we'll help you getting this done. To find out more about styling those pages, please find some instructions [here](https://github.com/oneworldmarket/idibu-api/blob/master/UPP/styling.md).

## Available parameters
Below is the list of available parameters, their description, and usage examples.<br/><strong>*</strong> denotes a parameter that is required.

### Account parameters
- `method` - please specify as "post" if you are proving parameters using HTTP POST. Otherwise, HTTP GET will be accepted.
- `hash`* - idibu account's hash
- `partnerId` - idibu partner ID, used for applying custom CSS and options on posting. Please contact us to obtain one.

### Sender parameters:
- `senderId`* - idibu account user's ID. You can use the following parameters instead to create a new user (`allowNewUsers`, see below) or auto-identify an existing one (`findUser`, see below):
   - `firstName`* - sender's first name
   - `lastName`* - sender's last name
   - `email`* - sender's e-mail address
- `phone`* - sender's phone number
- `www`* - sender's company www address
- `country`* - sender's country
- `postcode`* - sender's post code
- `company`* - sender's company name

### Job parameters:
- `boards` - list of board IDs to publish to, separated by semicolons (e.g. 37;151;123)
- `jobTitle` - job title (e.g. A%20test%20title)
- `jobRef` - job reference (e.g. REF123) - minimum 4 characters
- `startDate` - job start date in yyyy-mm-dd format with leading zeroes (e.g. 2013-06-25)
- `category` - ID of selected category (available options listed below, e.g. 13)
- `location` - ID of selected location (available options listed below, e.g. GB)
- `sublocation` - sublocation's name (e.g. London)
- `sublocationId` - sublocation's ID (e.g. 1024195)
- `mapPostCode` - instead of providing the ID or text value of a location, you can provide a post code as a location source. idibu will use Google's location API to figure out the intented location based on it. By default, we will try to map to UK post code, but if you provide the `location` variable (country code as listed below), the system will look for a location within the provided post code in the specified country.
- `hours` - working hours ID (available options listed below, e.g. 1)
- `term` - job type ID (available options listed below, e.g. 2)
- `duration` - contract duration (not available if `term` is set to "Permanent" (ID: 2), e.g. Two%20months)
- `currency` - salary currency's ISO-3 code (please use `US` instead of `USD` and `EU` instead of `EUR`; all other currencies should be valid 3-letter codes)
- `minSalary` - minimum salary (e.g. 2000)
- `maxSalary` - maximum salary (e.g. 3000)
- `per` - salary period (available options listed below, e.g. month)
- `extraBenefits` - extra benefits (e.g. premium%20health%20care)
- `salaryDescription` - optional salary text override (e.g. 2000%20pounds%20or%20more) - for most job boards, if used, this value will hide all the other salary data
- `appUrl` - optional URL to use if one wants to apply for the job
- `jobDesc` - job description (e.g. Here%20is%20a%20test%20description)

### Config paramters:
- `hideTitle` - Set to true to hide the job title field
- `hideRef` - Set to true to hide the job reference field
- `hideStartDate` - Set to true to hide the job start date field
- `hideAppUrl` - Set to true to hide the job application URL field
- `findUser` - Set to true if you want to get a user ID by their e-mail from idibu
- `findJob` - Set to false if you don't want to fetch job field values from old jobs based on reference
- `enablePreview` - Setting this to true triggers preview option on the step 2 of the posting process. Please use only with non-default styling.
- `useOriginalSender` - Comes together with the `findjob` parameter. The system will re-use the original sender of the ad.
- `overrideRepost` - Set to true if parameters from URL have higher priority than repost data (if `findJob` is set to true)
- `allowNewUsers` - set to true if you wish to create a new idibu user if an unknown email appears in the email field. True by default.

## Providing board-specific field values
The posting process is split into two steps. 

1. First, as part of the UPP interface, you provide all the Available parameters, as per the above. Parameters that haven't been pre-filled (and potentially hidden) when generating the page, can be normally filled by the user within the interface.
2. The second step - the [Post Completion Page](https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/pcp.md) - allows to fill in all the Extra Fields that are unique and specific to particular posting destinations. Despite these being handled by a separate page, you can provide values for them in advance while generating the UPP.<br/>To do that, you need to call the page with an additional `extrafields` parameter. Its contents need to be different for different boards and fields. You can find more info on how to obtain fields names, types and values, as well as all the other board-specific data [here](https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/board-specific-fields.md).<br/>The formats are explained below:

#### Single-select and text fields
`extrafields=(numeric board id)|(field name)|(field value)`

#### Multi-select fields
`extrafields=(numeric board id)|(field name)|(field value 1),(field value 2),`<br/>
notice that this format is always closed with a comma, even if you have provided a single value.

#### Double-select fields
`extrafields=(numeric board id)|(field name),(parent value)|(child value 1)`

#### Double-multi-select fields
`extrafields=(numeric board id)|(field name),(parent value)|(child value 1),(child value 2),`<br/>
notice that this format is always closed with a comma, even if you have provided a single value.

#### Providing multiple fields
Each field has to be sameparated with non-url encoded semicolon, for example:<br/>
`extrafields=118%7CLoctest%7C08;118%7Cparam%7Cedit;118%7Creqmultisel%7C1,2,;118%7Creqdmutli,1%7C1,2,;`<br/>
which translates to:<br/>
`extrafields=118|Loctest|08;118|param|edit;118|reqmultisel|1,2,;118|reqdmutli,1|1,2,;`

#### Escaping the comma
If you need to provide the comma (`,`) character as part of any extra field, please use `CDATA` to enclose the value, for example:<br/>
`118%7Creqtest%7C%3C!%5BCDATA%5BComma%2C%20separated%2C%20text%5D%5D%3E`<br/>
which translates to:<br/>
`extrafields=118|reqtest|<![CDATA[Comma, separated, text]]>;`

## Available field values

#### Category
See [Sectors](https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/Sector-and-locations.md#sectors).

#### Location:
See [Country codes](https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/Sector-and-locations.md#country-codes).

#### Job type:
`1` – Contract<br/>
`2` – Permanent<br/>
`4` – Temporary

#### Working hours:
`1` – Part-time<br/>
`2` – Full-time

#### Salary period:
`annum` – Annum<br/>
`month` – Month<br/>
`week` – Week<br/>
`day` – Day<br/>
`hour` - Hour
