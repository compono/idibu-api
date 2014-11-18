<p>Method returns offices list</p>
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
				<p class="p2">numeric offset from where to fetch offices, default is 0</p>
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
				<p class="p2">number of offices to return in response, default is 10</p>
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
http://ws.idibu.com/ws/rest/v1/offices?hash=<your hash>&count=100
</code></pre>
<h2>
	Response</h2>
<pre>
<code type="xml">
&lt;?xml version=&quot;1.0&quot; encoding=&quot;utf8&quot;?&gt;
&lt;idibu generator=&quot;idibu&quot; version=&quot;1.0&quot;&gt;
    &lt;response&gt;
        &lt;offices&gt;
            &lt;office&gt;
                &lt;id&gt;33000170&lt;/id&gt;
                &lt;name&gt;moldova&lt;/name&gt;
                &lt;contacts&gt;&lt;address&gt;xxx
xx
xxx, xxx
xxxxx&lt;/address&gt;
                    &lt;address-line1&gt;xxx&lt;/address-line1&gt;
                    &lt;address-line2&gt;xx&lt;/address-line2&gt;
                    &lt;address-line3&gt;xxx&lt;/address-line3&gt;
                    &lt;country&gt;xxx&lt;/country&gt;
                    &lt;postcode&gt;xxxxx&lt;/postcode&gt;
                    &lt;email&gt;x@x.pl&lt;/email&gt;
                    &lt;phone&gt;345678&lt;/phone&gt;
                    &lt;fax&gt;456789&lt;/fax&gt;
                    &lt;www&gt;www.w.ww&lt;/www&gt;
                &lt;/contacts&gt;
            &lt;/office&gt;
            &lt;office&gt;
                &lt;id&gt;33000178&lt;/id&gt;
                &lt;name&gt;Big office&lt;/name&gt;
                &lt;contacts&gt;&lt;address&gt;somewhere street 12

, Poland
83-333&lt;/address&gt;
                    &lt;address-line1&gt;somewhere street 12&lt;/address-line1&gt;
                    &lt;address-line2&gt;&lt;/address-line2&gt;
                    &lt;address-line3&gt;&lt;/address-line3&gt;
                    &lt;country&gt;Poland&lt;/country&gt;
                    &lt;postcode&gt;83-333&lt;/postcode&gt;
                    &lt;email&gt;bro.tru@gmail.com&lt;/email&gt;
                    &lt;phone&gt;234234&lt;/phone&gt;
                    &lt;fax&gt;&lt;/fax&gt;
                    &lt;www&gt;www.www.www&lt;/www&gt;
                &lt;/contacts&gt;
            &lt;/office&gt;
            &lt;office&gt;
                &lt;id&gt;33000182&lt;/id&gt;
                &lt;name&gt;test&lt;/name&gt;
                &lt;contacts&gt;&lt;address&gt;testes
tsetse
tsetset, stset
set&lt;/address&gt;
                    &lt;address-line1&gt;testes&lt;/address-line1&gt;
                    &lt;address-line2&gt;tsetse&lt;/address-line2&gt;
                    &lt;address-line3&gt;tsetset&lt;/address-line3&gt;
                    &lt;country&gt;stset&lt;/country&gt;
                    &lt;postcode&gt;set&lt;/postcode&gt;
                    &lt;email&gt;tse@pl.pl&lt;/email&gt;
                    &lt;phone&gt;987564231&lt;/phone&gt;
                    &lt;fax&gt;&lt;/fax&gt;
                    &lt;www&gt;46654654&lt;/www&gt;
                &lt;/contacts&gt;
            &lt;/office&gt;
        &lt;/offices&gt;
        &lt;total&gt;3&lt;/total&gt;
    &lt;/response&gt;
    &lt;status&gt;success&lt;/status&gt;
&lt;/idibu&gt;
</code></pre>
