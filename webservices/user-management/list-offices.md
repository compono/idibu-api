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

```xml
<?xml version="1.0" encoding="utf8"?>
<idibu generator="idibu" version="1.0">
    <response>
        <offices>
            <office>
                <id>33000170</id>
                <name>moldova</name>
                <contacts>
                    <address>xxx
                        xx
                        xxx, xxx
                        xxxxx
                    </address>
                    <address-line1>xxx</address-line1>
                    <address-line2>xx</address-line2>
                    <address-line3>xxx</address-line3>
                    <country>xxx</country>
                    <postcode>xxxxx</postcode>
                    <email>x@x.pl</email>
                    <phone>345678</phone>
                    <fax>456789</fax>
                    <www>www.w.ww</www>
                </contacts>
            </office>
            <office>
                <id>33000178</id>
                <name>Big office</name>
                <contacts>
                    <address>somewhere street 12
                        , Poland
                        83-333
                    </address>
                    <address-line1>somewhere street 12</address-line1>
                    <address-line2></address-line2>
                    <address-line3></address-line3>
                    <country>Poland</country>
                    <postcode>83-333</postcode>
                    <email>bro.tru@gmail.com</email>
                    <phone>234234</phone>
                    <fax></fax>
                    <www>www.www.www</www>
                </contacts>
            </office>
            <office>
                <id>33000182</id>
                <name>test</name>
                <contacts>
                    <address>testes
                        tsetse
                        tsetset, stset
                        set
                    </address>
                    <address-line1>testes</address-line1>
                    <address-line2>tsetse</address-line2>
                    <address-line3>tsetset</address-line3>
                    <country>stset</country>
                    <postcode>set</postcode>
                    <email>tse@pl.pl</email>
                    <phone>987564231</phone>
                    <fax></fax>
                    <www>46654654</www>
                </contacts>
            </office>
        </offices>
        <total>3</total>
    </response>
    <status>success</status>
</idibu>
```
