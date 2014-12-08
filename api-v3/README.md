### **Overview of the Adpost XML v3 API**

idibu API allows third parties to access the idibu posting engine by posting XML to our system.
That allows not only for a complete management of your job posting, but also allows excellent flexibility when it comes to the XML data package that you send.

Depending on the method employed you can either make a quick posting in a single XML or split this into two steps: Sending core field and completing the process by providing missing information using a Post Completion Page - PCP.  

The "Posting Completion Page" a regular web page where users provide any additional information required to complete a post and is:

- So simple that no training is required
- Designed to be completely re-branded and customized for partners including:

1. the posting url, allowing for fully brand-embedded posting to be integrated into third party systems.
2. the email box used for notifications, that can be configured so any standard SMTP email account can be used

The xml payload used to post to idibu split into 5 blocks of data, where 3 of them relates to the job itself and 1 to the boards intended to post. The blocks of data are grouped like this:

    Job data
        PCP configuration data
        Job core fields and dynamic core fields
        Sender and team information
    Board posting information

The description and usage of each group and its tags are explained below, with special emphasis in those tags that we consider more important for the posting process. You can view working examples here.

<a href="https://github.com/oneworldmarket/idibu-api/blob/master/api-v3/methods.md">1. Available methods.</a><br>
<a href="https://github.com/oneworldmarket/idibu-api/blob/master/api-v3/vars.md">2. API Variables.</a><br>
<a href="https://github.com/oneworldmarket/idibu-api/blob/master/api-v3/Sector-and-locations.md">2a. Sectors & Locations.</a><br>
<a href="https://github.com/oneworldmarket/idibu-api/blob/master/api-v3/spec-data.md">2b. Posting Destination Specific Data.</a><br>
<a href="https://github.com/oneworldmarket/idibu-api/blob/master/api-v3/dyn-vars.md">2c. Dynamic Variables.</a><br>
<a href="https://github.com/oneworldmarket/idibu-api/blob/master/api-v3/sender-tags.md">2d. Sender Tags.</a><br>
<a href="https://github.com/oneworldmarket/idibu-api/blob/master/api-v3/jobidvsjobref.md">3. Job ID Vs. Client Ref.</a><br>
<a href="https://github.com/oneworldmarket/idibu-api/blob/master/api-v3/pcp.md">4. Post Completion Page.</a><br>
<a href="https://github.com/oneworldmarket/idibu-api/blob/master/api-v3/sub-and-resp.md">5. Submitting and Responses.</a><br>
<a href="https://github.com/oneworldmarket/idibu-api/blob/master/api-v3/quick-rep-job.md">6. Quick Re-posting Data.</a><br>
<a href="https://github.com/oneworldmarket/idibu-api/blob/master/api-v3/canceling-pend-posts.md">7. Cancelling Pending Posts.</a><br>
<a href="https://github.com/oneworldmarket/idibu-api/blob/master/api-v3/delet-jobs.md">8. Deleting Posts.</a><br>
<a href="https://github.com/oneworldmarket/idibu-api/blob/master/api-v3/ref-based-delete.md">8a. Reference based delete.</a><br>
<a href="https://github.com/oneworldmarket/idibu-api/blob/master/api-v3/first-test-posting.md">9. First Posting.</a><br>
