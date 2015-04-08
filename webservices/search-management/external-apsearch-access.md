<p>Though a web-service for apsearch is not yet ready, we have created means for our partners to embed the idibu&#39;s CV search facility (Apsearch) inside their system at least in a basic way:</p>
<p><code>
POST/GET http://www.idibu.com/clients/apsearch.php?hash=(ACCOUNT HASH HERE)&profile=(USER PROFILE ID)
</code><br /><br />

	Which will allow you to access idibu&#39;s apsearch page without access to any other parts of idibu. If you don&#39;t provide a profile ID, you will login as admin.</p>
<p>Please note that in order to be using apsearch as a specific user, the user has to have a sub-account first. You can set this in the authenticate part of the <a href="http://www.idibuworld.com/docs/create-new-user-wsrestv1usersnew">add</a>/<a href="http://www.idibuworld.com/docs/show-user-profile-settings-and-auth-details-update-profilesettings-remove-user-wsrestv1users">edit </a>user WS.</p>
<p>One has to still login to idibu for apserarch options and subscription and options management.</p>
<p><img alt="" src="http://www.idibu.com/images/stories/Portal_logos/apsearch_preview.jpg" style="width: 636px; height: 442px;" /></p>
