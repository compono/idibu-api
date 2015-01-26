<h1>Introduction</h1>
Along the universal posting page idibu provides also ad oriented ad manager (in short: AO ad manager)<br />
<br />
<img src="http://www.idibu.com/images/stories/Portal_logos/aoadmanager.png" /><br />
<br />
This is a iframe-ready version of idibu`s ad manager that allows you to manage the posting status of your selected job. Thus this version won't show you status of all of your ads, but will show you te status one selected ad. This job will show you one entry per job board as long as you will keep a scenario where you only once make a new posting under specific job reference and then make sure you only use the repost method with the same job.
<h1>What does it all mean?</h1>
As you can see each post is described with a few parameters:<br />
<br />
a) Status: Live (post is safe on the board and provides applications - there will be a redirect "view" link to see the ad on the job board where possible.), Failed (Something went wrong when posting the ad, but no worries - we'll send some helpful guidelines on how to fix the problem once it occurs), Expired (When the expected live span of a post is completed) and Deleted (when you remove the post off job board from external boards).<br />
b) Posted to: Just the name of the job board you posted to<br />
c) Posted at<br />
d) Applicants: Total Number of applicants for a particular post (job board) - please note this will only show the number of applications if you have purchased you idibu license with Aptrack application tracking product and board does support this feature.<br />
e) Expires on<br />
<br />
Also, you have a variety of actions you can do with a particular posts (that can be triggered with the buttons on the right):<br />
<br />
a) Quick Repost: Just take a post and repost it with one click with all the same original details! No questions asked!<br />
b) Quick Repost Expired: Quick reposts all the expired posts, so you can refresh your job with hardly any effort.<br />
c) Full Repost: you can repost the position and amend some details on the way, just as if you posted a new job, but with all the details pre-filled. You can use that to, i.e. change jobs location to a more generic one i.e.<br />Please mind you will need to provide a repost URL, but we'll get to that!<br />
d) Delete Advert: It allows you to delete a particular post off the job board (provided the board supports such functionality)<br />
e) Delete All Adverts: Same as above, but for all applicable posts.
<h1>Time for the link?</h1>
<b>http://uk.idibu.com/clients/easyweb/index.php?</b>
<h1>What are the possible parameters?</h1>
h* - posting account hash<br />
ref* - reference of the job you wish to manage<br />
ins* - repost link (URL encoded). By default it will add two parameter to the provided request: J (with job id) and M with value R which stads for "method=repost". You can use this in your software to call your posting page to generate step1 identical as when posting a new ad, but that will use repost <a href="https://github.com/oneworldmarket/idibu-api/blob/master/api-v3/methods.md">API method</a> and the jobid from the J parameter. So the XML (selected fragment) should look like:<br>
<br>
<pre>
<code type="xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot;?&gt;
&lt;idibu&gt;
&lt;method&gt;repost&lt;/method&gt;
 &lt;config&gt;
...
 &lt;/config&gt;
&lt;job id=&quot;12345678&quot;&gt;
...
&lt;/job&gt;
&lt;/idibu&gt;
</code>
</pre>

You can use <a href="https://github.com/oneworldmarket/idibu-api/blob/master/webservices/advert-management/get-list-of-all-ads.md">idibu webservices</a> to download original posting`s details (like title, description, etc) and fill in the repost form of your software! <br><br>
It's even easier with UPP! Just provie this as your repost url:<br>

http://www.idibu.com/clients/easyweb/index.php?h=<b>(posting account hash)</b>2&ins=http%3A%2F%2Fwww.idibu.com%2Fclients%2Fupp%2Findex.php%3Fhash%3D<b>(posting account hash)</b>%26partnerid%3D<b>(your partner ID)</b>%26jobRef%3D<b>(job reference</b>&email=<b>(ad sender`s email)</b>

So esentially you just need to give UPP hash, job reference and sender and UPP will prepare a page ready to make the repost, already filled with original posting's details!
