## Dynamic Core Fields (DCF)

The idibu API incorporates a feature termed _Dynamic Core Fields_ (DCF) to enhance the integration process and simplify job posting. 

Unlike 'core' fields, DCFs are not mandatory for a successful job posting; however, they facilitate seamless integration and posting. These fields are universally applicable across different job boards and can be identified using the [board discovery service](https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/spec-data.md). Each `extrafield` XML tag connected to a DCF will have a `dynfield` attribute when [obtaining the data](https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/board-specific-fields.md).

The primary objective of these fields is to aggregate frequently recurring data found in job boards' specific 'extra fields', while still permitting customisation on a per-board basis when necessary.

In instances where a DCF is included within the XML payload, and if these fields are utilised by the boards to which the client plans to post, the values provided are employed to populate the corresponding job board 'extra fields' when they are absent from the request.

For instance, numerous job boards accept textual representations of start dates. If the preference is to display 'ASAP' as the start date instead of an explicit date, transmitting this information via the 'startDateOverride' field ensures that all supporting boards have their relative extra fields automatically propagated with the text-override supplied. It is, however, still possible to specify a per-board unique value in each job board's specific extra field if needed.

The list of fields is provided below, and practical usage examples can be found on the [examples page](https://github.com/oneworldmarket/idibu-api/tree/master/posting-api/examples).

**Disclaimer:** Please keep in mind that every job board may utilize the fields (particularly the Override ones) a bit differently in its interface and the back-end; idibu does not track this information.

### Field list

| Field name        | Data type    | Label               | Description                                                                                                                                                               |
|-------------------|--------------|---------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| app_url           | string (URL) | Application URL     | URL of an external page to which candidates will be redirected instead of using the board's default application functionality.                                            |
| salaryOverride    | string       | Salary Override     | Textual description of the salary; on most job boards, this will replace the display of the full salary information while still using the other salary fields for search. |
| startDateOverride | string       | Start Date Override | Textual description of when the candidate would begin working; on most job boards, this will replace the date provided in the `startdate` field.                          |
