_**This document is outdated. Please refer to the new version [HERE](https://github.com/oneworldmarket/idibu-api/blob/master/webservices/advert-management/advert-management-webservice.md).**_

<details>
 <summary><i>Show me anyway</i></summary>
   
Allows you to identify jobs with expiring posts in relation to current day.

Call you should make:

/rest/v1/adverts/n/days-expiring will show adverts expiring in n days, for example:

    /rest/v1/adverts/0/days-expiring - adverts expiring today,
    /rest/v1/adverts/1/days-expiring - adverts expiring tomorrow,
    /rest/v1/adverts/7/days-expiring - adverts expiring in 7 days.

</details>
