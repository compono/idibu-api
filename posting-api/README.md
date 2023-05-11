## Overview of the Adpost XML posting API

This documentation provides a comprehensive overview of the idibu Adpost XML posting API, which enables third-party access to the idibu posting engine via XML submissions. By utilising this API, not only can users exercise full control over their job postings, but they can also benefit from the enhanced flexibility of the XML data package they provide.

### XML Posting Process
The XML posting process can be executed in either a single step or two steps depending on the method employed. The former allows for a rapid job posting by submitting a single XML package, while the latter divides the posting process into two stages. In the second stage, users are redirected to a Posting Completion Page (PCP) where they can provide any missing information (i.e job-board-specific extra-fields) needed to complete the post.

### Posting Completion Page
The Posting Completion Page is a standard web page that enables users to provide the additional job-board-specific information required to complete a post. It is designed to be user-friendly, with no training required. Moreover, it is fully rebrandable and customisable for partners to allow for seamless integration with third-party systems.

### XML Payload Data:
The XML payload is divided into five blocks of data. Three blocks relate to the job itself, one to the intended job board posting, and one to the PCP configuration. These blocks of data are grouped in the following order:

1. Job Data
2. PCP Configuration Data
3. Job Core Fields and Dynamic Core Fields
4. Sender and Team Information
5. Board Posting Information

The documentation provides an explanation of each group and its XML tags, with particular emphasis on the most significant ones in the submission process, with working examples included.

### API Functionality:
The documentation provides a detailed overview of the available methods, API variables, and dynamic variables that can be utilized to customize the XML package. It also discusses the various data elements that can be employed to post jobs to specific destinations, cancel or delete pending posts, and perform first postings.

1. [Available methods](https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/methods.md)  
2. [API variables](https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/vars.md)  
   2a. [Sectors & Locations](https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/Sector-and-locations.md)  
   2b. [Posting destination specific data](https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/spec-data.md)  
   2c. [Dynamic variables](https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/dyn-vars.md)  
   2d. [Sender tags](https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/sender-tags.md)
3. [Job ID vs. Client Ref](https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/jobidvsjobref.md)
4. [Posting Completion Page](https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/pcp.md)
5. [Submitting, encoding, and responses](https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/sub-and-resp.md)
6. [Quick reposting](https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/quick-rep-job.md)
7. [Cancelling pending posts](https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/canceling-pend-posts.md)
8. [Deleting posts](https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/delet-jobs.md)  
   8a. [Reference-based delete](https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/ref-based-delete.md)
9. [First posting](https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/first-test-posting.md)

### Conclusion:
The Adpost XML posting API offers a powerful tool for third-party access to the idibu posting engine. By utilising this API, users can exercise complete control over their job postings while benefiting from enhanced flexibility. The document provides a comprehensive overview of the API's functionality and features, including the Posting Completion Page, XML payload data, and API functionality.
