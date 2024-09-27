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
https://ws.idibu.com/ws/rest/v1/users?hash=<your hash>&count=100
</code></pre>
<h2>
	Response</h2>
	
```xml
<?xml version="1.0" encoding="utf8"?>
<idibu generator="idibu" version="1.0">
    <response>
        <users>
            <user>
                <id>485</id>
                <title></title>
                <firstname>vit</firstname>
                <lastname>Dyatlov</lastname>
                <company>Idibu</company>
                <team-id>33000183</team-id>
                <contacts>
                    <address>Tiraspol
                        , Moldova
                        3357
                    </address>
                    <address-line1>Tiraspol</address-line1>
                    <address-line2></address-line2>
                    <address-line3></address-line3>
                    <country>Moldova</country>
                    <postcode>3357</postcode>
                    <email>vitaly@idibu.com</email>
                    <phone>+373 0 777 15818</phone>
                    <fax></fax>
                    <www>idibu.com</www>
                </contacts>
            </user>
            <user>
                <id>1058</id>
                <title></title>
                <firstname>Bart</firstname>
                <lastname>Jaworski</lastname>
                <company>Idibu</company>
                <team-id>33000171</team-id>
                <contacts>
                    <address>Tiraspol
                        Strixton
                        , Moldova
                        3357
                    </address>
                    <address-line1>Tiraspol</address-line1>
                    <address-line2>Strixton</address-line2>
                    <address-line3></address-line3>
                    <country>Moldova</country>
                    <postcode>3357</postcode>
                    <email>vitaly@idibu.com</email>
                    <phone>+373 0 777 15818</phone>
                    <fax>01933665943</fax>
                    <www>idibu.com</www>
                </contacts>
            </user>
            <user>
                <id>1066</id>
                <title></title>
                <firstname>tt</firstname>
                <lastname>O&amp;#39;Hanlon (Birmingham)</lastname>
                <company>set</company>
                <team-id>33000183</team-id>
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
                    <email>bro.tru@gmail.com</email>
                    <phone>987564231</phone>
                    <fax></fax>
                    <www>46654654</www>
                </contacts>
            </user>
            <user>
                <id>1101</id>
                <title></title>
                <firstname>steve</firstname>
                <lastname>walker</lastname>
                <company>set</company>
                <team-id>33000183</team-id>
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
                    <email>steve@idibu.com</email>
                    <phone>987564231</phone>
                    <fax></fax>
                    <www>46654654</www>
                </contacts>
            </user>
            <user>
                <id>1168</id>
                <title></title>
                <firstname>Erico</firstname>
                <lastname>Lendzian</lastname>
                <company>xxx</company>
                <team-id>33000183</team-id>
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
                    <email>erico.idibu@gmail.com</email>
                    <phone>345678</phone>
                    <fax>456789</fax>
                    <www>www.w.ww</www>
                </contacts>
            </user>
            <user>
                <id>1197</id>
                <title></title>
                <firstname>new-user</firstname>
                <lastname></lastname>
                <company></company>
                <team-id>0</team-id>
                <contacts>
                    <address-line1></address-line1>
                    <address-line2></address-line2>
                    <address-line3></address-line3>
                    <country></country>
                    <postcode></postcode>
                    <email></email>
                    <phone></phone>
                    <fax></fax>
                    <www></www>
                </contacts>
            </user>
        </users>
        <total>8</total>
    </response>
    <status>success</status>
</idibu>
```
