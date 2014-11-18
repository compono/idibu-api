<p>Method returns user list</p>
<h1>
	Parameters</h1>
<table cellpadding="2" cellspacing="0" class="t1" width="1084.0">
	<thead>
		<tr>
			<th class="td1" scope="col" valign="middle">
				<p class="p1"><b>Parameter Name</b></p>
			</th>
			<th class="td2" scope="col" valign="middle">
				<p class="p1"><b>Required?</b></p>
			</th>
			<th class="td3" scope="col" valign="middle">
				<p class="p1"><b>Notes</b></p>
			</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td class="td1" valign="middle">
				<p class="p2">offset</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">numeric offset from where to fetch users, default is 0</p>
			</td>
		</tr>
		<tr>
			<td class="td1" valign="middle">
				<p class="p2">count</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">number of users to return in response, default is 10</p>
			</td>
		</tr>
		<tr>
			<td class="td1" valign="middle">
				<p class="p2">team-id</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">filter users by team</p>
			</td>
		</tr>
		<tr>
			<td class="td1" valign="middle">
				<p class="p2">office-id</p>
			</td>
			<td class="td2" valign="middle">
				<p class="p2">No</p>
			</td>
			<td class="td3" valign="middle">
				<p class="p2">filter users by office</p>
			</td>
		</tr>
	</tbody>
</table>
<h1>
	Example</h1>
<h2>
	Request</h2>
<pre>
<code>
http://ws.idibu.com/ws/rest/v1/users?hash=<your hash>&count=100
</code></pre>
<h2>
	Response</h2>
<pre>
<code type="xml">
&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
    &lt;response&gt;
        &lt;users&gt;
            &lt;user&gt;
                &lt;id&gt;485&lt;/id&gt;&lt;title&gt;&lt;/title&gt;
                &lt;firstname&gt;vit&lt;/firstname&gt;
                &lt;lastname&gt;Dyatlov&lt;/lastname&gt;
                &lt;company&gt;Idibu&lt;/company&gt;
                &lt;team-id&gt;33000183&lt;/team-id&gt;
                &lt;contacts&gt;&lt;address&gt;Tiraspol

, Moldova
3357&lt;/address&gt;
                    &lt;address-line1&gt;Tiraspol&lt;/address-line1&gt;
                    &lt;address-line2&gt;&lt;/address-line2&gt;
                    &lt;address-line3&gt;&lt;/address-line3&gt;
                    &lt;country&gt;Moldova&lt;/country&gt;
                    &lt;postcode&gt;3357&lt;/postcode&gt;
                    &lt;email&gt;vitaly@idibu.com&lt;/email&gt;
                    &lt;phone&gt;+373 0 777 15818&lt;/phone&gt;
                    &lt;fax&gt;&lt;/fax&gt;
                    &lt;www&gt;idibu.com&lt;/www&gt;
                &lt;/contacts&gt;
            &lt;/user&gt;
            &lt;user&gt;
                &lt;id&gt;1058&lt;/id&gt;&lt;title&gt;&lt;/title&gt;
                &lt;firstname&gt;Bart&lt;/firstname&gt;
                &lt;lastname&gt;Jaworski&lt;/lastname&gt;
                &lt;company&gt;Idibu&lt;/company&gt;
                &lt;team-id&gt;33000171&lt;/team-id&gt;
                &lt;contacts&gt;&lt;address&gt;Tiraspol
Strixton
, Moldova
3357&lt;/address&gt;
                    &lt;address-line1&gt;Tiraspol&lt;/address-line1&gt;
                    &lt;address-line2&gt;Strixton&lt;/address-line2&gt;
                    &lt;address-line3&gt;&lt;/address-line3&gt;
                    &lt;country&gt;Moldova&lt;/country&gt;
                    &lt;postcode&gt;3357&lt;/postcode&gt;
                    &lt;email&gt;vitaly@idibu.com&lt;/email&gt;
                    &lt;phone&gt;+373 0 777 15818&lt;/phone&gt;
                    &lt;fax&gt;01933665943&lt;/fax&gt;
                    &lt;www&gt;idibu.com&lt;/www&gt;
                &lt;/contacts&gt;
            &lt;/user&gt;
            &lt;user&gt;
                &lt;id&gt;1066&lt;/id&gt;&lt;title&gt;&lt;/title&gt;
                &lt;firstname&gt;tt&lt;/firstname&gt;
                &lt;lastname&gt;O\&amp;#39;Hanlon (Birmingham)&lt;/lastname&gt;
                &lt;company&gt;set&lt;/company&gt;
                &lt;team-id&gt;33000183&lt;/team-id&gt;
                &lt;contacts&gt;&lt;address&gt;testes
tsetse
tsetset, stset
set&lt;/address&gt;
                    &lt;address-line1&gt;testes&lt;/address-line1&gt;
                    &lt;address-line2&gt;tsetse&lt;/address-line2&gt;
                    &lt;address-line3&gt;tsetset&lt;/address-line3&gt;
                    &lt;country&gt;stset&lt;/country&gt;
                    &lt;postcode&gt;set&lt;/postcode&gt;
                    &lt;email&gt;bro.tru@gmail.com&lt;/email&gt;
                    &lt;phone&gt;987564231&lt;/phone&gt;
                    &lt;fax&gt;&lt;/fax&gt;
                    &lt;www&gt;46654654&lt;/www&gt;
                &lt;/contacts&gt;
            &lt;/user&gt;
            &lt;user&gt;
                &lt;id&gt;1101&lt;/id&gt;&lt;title&gt;&lt;/title&gt;
                &lt;firstname&gt;steve&lt;/firstname&gt;
                &lt;lastname&gt;walker&lt;/lastname&gt;
                &lt;company&gt;set&lt;/company&gt;
                &lt;team-id&gt;33000183&lt;/team-id&gt;
                &lt;contacts&gt;&lt;address&gt;testes
tsetse
tsetset, stset
set&lt;/address&gt;
                    &lt;address-line1&gt;testes&lt;/address-line1&gt;
                    &lt;address-line2&gt;tsetse&lt;/address-line2&gt;
                    &lt;address-line3&gt;tsetset&lt;/address-line3&gt;
                    &lt;country&gt;stset&lt;/country&gt;
                    &lt;postcode&gt;set&lt;/postcode&gt;
                    &lt;email&gt;steve@idibu.com&lt;/email&gt;
                    &lt;phone&gt;987564231&lt;/phone&gt;
                    &lt;fax&gt;&lt;/fax&gt;
                    &lt;www&gt;46654654&lt;/www&gt;
                &lt;/contacts&gt;
            &lt;/user&gt;
            &lt;user&gt;
                &lt;id&gt;1168&lt;/id&gt;&lt;title&gt;&lt;/title&gt;
                &lt;firstname&gt;Erico&lt;/firstname&gt;
                &lt;lastname&gt;Lendzian&lt;/lastname&gt;
                &lt;company&gt;xxx&lt;/company&gt;
                &lt;team-id&gt;33000183&lt;/team-id&gt;
                &lt;contacts&gt;&lt;address&gt;xxx
xx
xxx, xxx
xxxxx&lt;/address&gt;
                    &lt;address-line1&gt;xxx&lt;/address-line1&gt;
                    &lt;address-line2&gt;xx&lt;/address-line2&gt;
                    &lt;address-line3&gt;xxx&lt;/address-line3&gt;
                    &lt;country&gt;xxx&lt;/country&gt;
                    &lt;postcode&gt;xxxxx&lt;/postcode&gt;
                    &lt;email&gt;erico.idibu@gmail.com&lt;/email&gt;
                    &lt;phone&gt;345678&lt;/phone&gt;
                    &lt;fax&gt;456789&lt;/fax&gt;
                    &lt;www&gt;www.w.ww&lt;/www&gt;
                &lt;/contacts&gt;
            &lt;/user&gt;
            &lt;user&gt;
                &lt;id&gt;1197&lt;/id&gt;&lt;title&gt;&lt;/title&gt;
                &lt;firstname&gt;new-user&lt;/firstname&gt;
                &lt;lastname&gt;&lt;/lastname&gt;
                &lt;company&gt;&lt;/company&gt;
                &lt;team-id&gt;0&lt;/team-id&gt;
                &lt;contacts&gt;
                    
                    &lt;address-line1&gt;&lt;/address-line1&gt;
                    &lt;address-line2&gt;&lt;/address-line2&gt;
                    &lt;address-line3&gt;&lt;/address-line3&gt;
                    &lt;country&gt;&lt;/country&gt;
                    &lt;postcode&gt;&lt;/postcode&gt;
                    &lt;email&gt;&lt;/email&gt;
                    &lt;phone&gt;&lt;/phone&gt;
                    &lt;fax&gt;&lt;/fax&gt;
                    &lt;www&gt;&lt;/www&gt;
                &lt;/contacts&gt;
            &lt;/user&gt;
        &lt;/users&gt;
        &lt;total&gt;8&lt;/total&gt;
    &lt;/response&gt;
    &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
