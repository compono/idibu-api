<p>Method gets or sets system settings for an account</p>
<h1>
	Parameters</h1>
<p>No additional parameters for this request</p>
<h1>
	Example of getting settings</h1>
<h2>
	Request</h2>
<pre>
<code>
http://ws.idibu.com/ws/rest/v1/settings/system?hash=<your hash>
</code></pre>
<h2>
	Response</h2>
<pre>
<code type="xml">
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
  &lt;response&gt;
    &lt;general&gt;
      &lt;description&gt;
There are a number of system settings that can be changed to customise your idibu system. Please be sure to contact support if you aren&amp;#39;t completely sure of what you are doing.
&lt;/description&gt;
      &lt;cv-search-enabled&gt;yes&lt;/cv-search-enabled&gt;
      &lt;delete-enabled&gt;yes&lt;/delete-enabled&gt;
      &lt;force-check-spelling&gt;no&lt;/force-check-spelling&gt;
      &lt;show-advert-cost&gt;no&lt;/show-advert-cost&gt;
    &lt;/general&gt;
    &lt;user-access&gt;
      &lt;description&gt;
Change settings to provide non-admin users different levels of access to the system.
&lt;/description&gt;
      &lt;filter-profile-jobs&gt;yes&lt;/filter-profile-jobs&gt;
      &lt;disable-default-post-profile&gt;no&lt;/disable-default-post-profile&gt;
      &lt;strip-phone-numbers&gt;yes&lt;/strip-phone-numbers&gt;
      &lt;disable-normal-repost&gt;no&lt;/disable-normal-repost&gt;
      &lt;disable-quick-repost&gt;no&lt;/disable-quick-repost&gt;
      &lt;disable-job-template&gt;no&lt;/disable-job-template&gt;
    &lt;/user-access&gt;
    &lt;adverts&gt;
      &lt;description&gt;
Define advert authorisation policies for the account, and the email template informing senders if their advert was rejected.
&lt;/description&gt;
      &lt;adv-auth-policy&gt;yes&lt;/adv-auth-policy&gt;
      &lt;adv-auth-send-email-if-rejected&gt;yes&lt;/adv-auth-send-email-if-rejected&gt;
      &lt;email-template-reject&gt;
        &lt;subject&gt;subject of auth message&lt;/subject&gt;&amp;lt;body&amp;gt;Body of auth message&amp;lt;/body&amp;gt;
      &lt;/email-template-reject&gt;
      &lt;email-template-auth&gt;
        &lt;subject&gt;&lt;/subject&gt;&amp;lt;body&amp;gt;&amp;lt;/body&amp;gt;&lt;/email-template-auth&gt;
    &lt;/adverts&gt;
    &lt;alerts&gt;
      &lt;description&gt;
idibu provides important alerts by email - for posting errors and for when adverts are expiring on the job boards. You can set these alerts to be sent the sender of the advert, the administrator of this account, or both.
&lt;/description&gt;
      &lt;auto-error-mode&gt;Both&lt;/auto-error-mode&gt;
      &lt;auto-expiry-emails&gt;Both&lt;/auto-expiry-emails&gt;
    &lt;/alerts&gt;
    &lt;country&gt;
      &lt;description&gt;
Set the default country to be used by locations in the system.
&lt;/description&gt;
      &lt;location-country&gt;GB&lt;/location-country&gt;
    &lt;/country&gt;&lt;footer&gt;
      &lt;description&gt;
Add text to be appended to all job descriptions sent out by the system (Note, this can increase likelihood of boards rejecting adverts for description length).
&lt;/description&gt;
      &lt;jobdisclaimer&gt;
    &lt;/jobdisclaimer&gt;&lt;/footer&gt;
  &lt;/response&gt;
  &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
<h1>
	Example of setting settings</h1>
<h2>
	Request</h2>
<pre>
<code>
POST http://ws.idibu.com/ws/rest/v1/settings/system?hash=<your hash>
</code>
<code type="xml">
&lt;?xml version=&quot;1.0&quot;?&gt;
&lt;idibu&gt;
  &lt;cv-search-enabled&gt;yes&lt;/cv-search-enabled&gt;
  &lt;email-template-auth&gt;
    &lt;subject&gt;subject of auth message&lt;/subject&gt;&amp;lt;body&amp;gt;Body of auth message&amp;lt;/body&amp;gt;
  &lt;/email-template-auth&gt;
&lt;/idibu&gt;
</code>
</pre>
<h2>
	Response</h2>
<pre>
<code type="xml">
&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
  &lt;response&gt;
    &lt;message&gt;Settings updated&lt;/message&gt;
  &lt;/response&gt;
  &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code>
</pre>
<h1>
	idibu interface reference</h1>
<p><img alt="" src="http://uk.idibu.com/images/stories/Portal_logos/idibu_set_ref.jpg" /></p>
