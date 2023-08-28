## Dynamic Core Fields (DCF)

The idibu API incorporates a feature termed as Dynamic Core Fields (DCF) to enhance the integration process and simplify job posting. 

Unlike 'core' fields, DCFs are not mandatory for a successful job posting; however, they facilitate seamless integration and posting. These fields are universally applicable across different job boards and can be identified using the <a href="https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/spec-data.md">board discovery service</a>.</p>

The primary objective of these fields is to aggregate frequently recurring data found in job boards specific 'extra fields', while still permitting customisation on a per-board basis when necessary.

In instances where a DCF is included within the XML payload, and if these fields are utilised by the boards to which the client plans to post, the values provided are employed to populate the corresponding job board 'extra fields' when they are absent from the request.

For instance, numerous job boards accept textual representations of start dates. If the preference is to display 'ASAP' as the start date instead of an explicit date, transmitting this information via the 'startDateOverride' field ensures that all supporting boards have their relative extra fields automatically propogated with the text-override supplied. The list of fields is provided below, and practical usage examples can be found on the <a href="https://github.com/oneworldmarket/idibu-api/tree/master/posting-api/examples">examples page</a>.</p>

**Field List:**

- **Field Name:** startDateOverride
  - **Data Type:** text
  - **Description:** Start Date Description/Override

- **Field Name:** salaryOverride
  - **Data Type:** text
  - **Description:** Salary Description/Override. Please place this tag below other Salary override tags.

- **Field Name:** app_url
  - **Data Type:** text
  - **Description:** Application URL
