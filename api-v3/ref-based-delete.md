You can also delete repost your clients ads based on reference alone - sending a single request will then remove the ad from all portals where that is possible. However we recommend to use this option ONLY if your system is based on a unique reference per each job. Otherwise you may end up removing posts that were not indended for delete

**POST** clients/api/REMOTE/V3?hash=&lt;client_hash&gt;

<code> 
&lt;idibu&gt;<br>
&nbsp; &nbsp;&lt;method&gt;delete&lt;/method&gt;<br>
&nbsp; &nbsp;&lt;job ref=&quot;job_reference&quot;&gt;&lt;/job&gt;<br>
&lt;/idibu&gt;<br>
</code>

This method by default has a failsafe that will throw down an error in case a particular reference is connected to more then one job id. However this failsafe can be avoided by adding the All=yes parameter. Please mind that it is partners responsibility to build a system that won't accidentally delete any posts that should not be deleted using this method.

**POST** clients/api/REMOTE/V3?hash=&lt;client_hash&gt;

<code>
&lt;idibu&gt;<br>
&nbsp;&nbsp;&lt;method&gt;delete&lt;/method&gt;<br>
&nbsp;&nbsp;&lt;job ref=&quot;job_reference&quot; all=&quot;yes&quot;&gt;&lt;/job&gt;<br>
&lt;/idibu&gt;
</code>
