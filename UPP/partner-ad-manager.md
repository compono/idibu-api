# Introduction
Along with the [Universal Posting Page](https://github.com/oneworldmarket/idibu-api/tree/master/UPP), idibu also provides an AdManager.

![image](https://www.idibu.com/images/stories/Portal_logos/aoadmanager.png)

This is an iframe-ready tool that allows to manage a selected job. It will not show the status of all of the ads - just one selected. To ensure convenient usage, **please make sure to always keep Job Reference unique across all adverts (jobs) on each account**!

# Functionality
## Indicators
- **Status**
   - _Live_ - Successfully posted. There may be a clickable link to view the ad on the website if the job board supports this.
   - _Failed_ - Something went wrong when posting the ad. If it is a known issue, we'll send some helpful guidelines to the user on how to fix the problem.
   - _Expired_ - When the post reaches its expiry date.
   - _Deleted_ - Successfully removed.
- **Posted to** - The name of the website on which the advert has been posted / deleted.
- **Posted at** - The exact time of the posting / deletion, in UK timezone.
- **Applicants** - Total number of candidates from the particular website. Please note this will only show the number of applications if you are using Aptrack and the website in question supports this feature.<br />
- **Expires on** - When the post will expire on the website, in UK timezone.

## Actions
- **Quick Repost** - Reposts the selected advert with exactly the same details in one click.
- **Quick Repost Expired** - Quick reposts all currently expired posts, allowing to refresh the job on all websites with just a single click.
- **Full Repost** - Allows to repost the selected advert and amend some details on the way, just like when posting a new job but with all the previous data pre-filled.
- **Delete Advert** - Removes a particular post from the website (provided the website supports such functionality).
- **Delete All Adverts** - Same as above, but for all applicable posts (ones that are currently active on websites that support deleting).

# Generating the AdManager
## Endpoint
https://www.idibu.com/clients/pam/index.php

## Parameters
- **`h`** - _(required)_ - posting account's hash
- **`ref`** - _(required)_ - reference of the job to manage
- **`ins`** - _(required)_ - the repost link. You can use this in your software to generate your repost page same as when posting a new ad. By default, two parameters will be added to the provided URL:
   - `J` - job ID
   - `M` - will take value of `R` which stands for "REPOST" (see [API methods](https://github.com/oneworldmarket/idibu-api/blob/master/posting-api/methods.md) for more info)
- **`noRepostParameters`** - _(optional)_ - if set to `true`, no `J` and `M=R` parameters will be appended to the `ins` URL on full repost
- **`sameWindow`** - _(optional)_ - if set to `true`, the Full Repost action will open a page in the current window instead of a new tab
- **`s`** - _(optional)_ - your partner ID if you wish to utilize custom styling

## Managing and Reposting the ads
You can use the [Advert Management Webservice](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/advert-management/advert-management-webservice.md) and [Job Management Webservice](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/job-management/job-management-webservice.md) to obtain all the posting's details (like title, description, etc.) and fill in more data inside your software based on that.

It's even easier with [UPP](https://github.com/oneworldmarket/idibu-api/tree/master/UPP) - simply by inserting it as the `ins` parameter. For example:

`https://www.idibu.com/clients/pam/index.php?h=ACCOUNT_HASH&ref=JOB_REFERENCE&ins=https%3A%2F%2Fwww.idibu.com%2Fclients%2Fupp%2Findex.php%3Fhash%3DACCOUNT_HASH%26jobRef%3DJOB_REFERENCE%26useOriginalSender%3Dtrue%26findJob%3Dtrue`

This would generate an AdManager with a repost-ready UPP under the "Full Repost" button, with all the original details of the posting already pre-filled.
