This webservice allows to manage (create, obtain, or remove) webhook subscriptions for various types of events that can occur in idibu system.

A webhook is an HTTP request that idibu system will send to a URL defined by you, whenever some event(s) chosen by you for the given webhook occur.

Each event type comes with its own set of HTTP parameters present in the body of the request - the parameters define various objects (e.g. [Adverts](https://github.com/oneworldmarket/idibu-api/tree/master/webservices/advert-management), [Candidates](https://github.com/oneworldmarket/idibu-api/tree/master/webservices/applicant-management), [Jobs](https://github.com/oneworldmarket/idibu-api/tree/master/webservices/job-management), [Users](https://github.com/oneworldmarket/idibu-api/tree/master/webservices/user-management)) related to the event that can be further queried and managed using other webservices.
