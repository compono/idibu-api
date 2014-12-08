<h1>What is UPP?</h1>
<p>UPP stands for Uninersal Posting Page. Essentially it's all ready PHP page with idibu multiposting functionality giving you all the options you need to use with your system. All needed to be done here is to style up the page, so it looks like it was developed by you, but you can have posting working in your system withing minutes!</p>
<h1>How to use it?</h1></p>
<p>Simply make a call to a link below with required paramaters. To make it super smooth you will need to map a few idibu parameters with your own vaiables.</p>
<h1>Posting URL</h1>
<p><br />All parameters can be provided in either a traditional HTTP GET or POST fashion and must be URL encoded. POST is recommended to get pass any character count limits typical for GET method. For example, in order to provide the hash, sender ID and job title into the system located at partners.idibu.com, you should use the following URL:</p>
<p><br /><a class="linkification-ext" title="Linkification: http://www.idibu.com/clients/upp/index.php?hash=yourhash&amp;senderId=123&amp;jobTitle=test%20title" href="http://www.idibu.com/clients/upp/index.php?hash=yourhash&senderId=123&jobTitle=test%20title">http://www.idibu.com/clients/upp/index.php?hash=yourhash&amp;senderId=123&amp;jobTitle=test%20title</a></p>
<h1>Styling</h1>
Here is how this can be looked when styling is applied:
<a href="http://www.idibu.com/clients/upp/index.php?hash=yourhash&senderId=123&jobTitle=test%20title&partnerId=bond">http://www.idibu.com/clients/upp/index.php?hash=yourhash&senderId=123&jobTitle=test%20title&partnerId=bond</a>
Just <a href="mailto:good@idibu.com">contact us</a> to become a partner and we'll help you getting this done.
<h1>Available parameters</h1></p>
<p><br />Here&rsquo;s the list of available parameters, their description and usage examples - - * denotes a parameter that is required.</p>
<p><br /><span style="font-size: large;">Account parameters:</span></p>
<ul>
<li>hash* - idibu account hash</li>
<li>partnerId - idibu partner ID, used for applying custom CSS and options on posting. Please contact us to obtain one.</li>
<li>Sender parameters:</li>
<li>senderId* &ndash; idibu user ID (can input sender's first name, last name and e-mail instead)</li>
</ul>
<p>OR (if senderId not provided)</p>
<ul>
<li>firstName* - sender's first name </li>
<li>lastName* - sender's last name</li>
<li>email* - sender's e-mail address</li>
<li><span class="wrapper"><span class="content"><span class="content_for_perma">phone* - sender's phone number<br /></span></span></span></li>
<li><span class="wrapper"><span class="content"><span class="content_for_perma">www* - sender's company www address</span></span></span></li>
<li><span class="wrapper"><span class="content"><span class="content_for_perma">country* - sender's country<br /></span></span></span></li>
<li><span class="wrapper"><span class="content"><span class="content_for_perma">postcode* - sender's post code<br /></span></span></span></li>
<li><span class="wrapper"><span class="content"><span class="content_for_perma">company* - sender's company name<br /></span></span></span></li>
</ul>
<p><br /><span style="font-size: large;">Job parameters:</span></p>
<ul>
<li>boards - list of board ID's to publish to, separated by commas (e.g. 37,151,123)</li>
<li>jobTitle - job title (e.g. A%20test%20title)</li>
<li>jobRef - job reference (e.g. REF123)</li>
<li>startDate &ndash; job start date in yyyy-mm-dd format with leading zeroes (e.g. 2013-06-25)</li>
<li>category - ID of selected category (available options listed below, e.g. 13)</li>
<li>location - ID of selected location (available options listed below, e.g. GB)</li>
<li>sublocation &ndash; sublocation&rsquo;s name (e.g. London)</li>
<li>sublocationId &ndash; sublocation&rsquo;s ID (e.g. 1024195)</li>
<li>term - employment term ID (available options listed below, e.g. 1)</li>
<li>duration - contract duration (only if employment term is set to "Contract" (ID: 1), e.g. Two%20months)</li>
<li>currency - salary currency ID (available options listed below, e.g. GBP)</li>
<li>minSalary - minimum salary (e.g. 2000)</li>
<li>maxSalary &ndash; maximum salary (e.g. 3000)</li>
<li>per - salary payment interval (e.g. month)</li>
<li>extraBenefits &ndash; extra benefits (e.g. premium%20health%20care)</li>
<li>salaryDescription &ndash; optional salary text override (e.g. 2000%20pounds%20or%20more)</li>
<li>appUrl &ndash; optional URL to use if one wants to apply for the job</li>
<li>jobDesc &ndash; job description (e.g. Here%20is%20a%20test%20description)</li>
</ul>
<p>&nbsp;</p>
<p><span style="font-size: large;">Config paramters:</span></p>
<ul>
<li>hideTitle - Set to true to hide job title field</li>
<li>hideRef - Set to true to hide job reference field</li>
<li>hideStartDate - Set to true to hide job start date field</li>
<li>hideAppUrl - Set to true to hide job application URL field</li>
<li>findUser - Set to true if you want to get a user ID by his e-mail from idibu</li>
<li>findJob - Set to false if you don't want to fetch job field values from old jobs based on reference</li>
<li>overrideRepost - Set to true if parameters from URL have higher priority than repost data (if findJob is set to true)</li>
<li>allowNewUsers - set to true if you like UPP to create a new idibu user if an unknown email appears in the email field. Set true as default.</li>
</ul>
