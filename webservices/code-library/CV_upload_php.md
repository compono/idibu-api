<p><strong>This code allows you to upload a candidate to specific job in idibu with possibility of source tracking. Details can be found <a href="https://github.com/oneworldmarket/idibu-api/blob/master/webservices/applicant-management/cv-upload-parsing.md">here</a>.</strong></p>

<pre>
<code>
&lt;?php
$JOB_ID = &#39;&#39;;
$HASH = &#39;&#39;;

if ($_FILES[&#39;cv&#39;]) {
    header(&#39;Content-Type: application/xml&#39;);

    $cvName = $_FILES[&#39;cv&#39;][&#39;name&#39;];
    $cvFile = base64_encode(file_get_contents($_FILES[&#39;cv&#39;][&#39;tmp_name&#39;]));

    $xml = &lt;&lt;&lt;XML
&lt;data&gt;
    &lt;job&gt;
        &lt;id&gt;$JOB_ID&lt;/id&gt;
    &lt;/job&gt;
    &lt;cv&gt;
        &lt;name&gt;&lt;![CDATA[$cvName]]&gt;&lt;/name&gt;
        &lt;contents&gt;$cvFile&lt;/contents&gt;
    &lt;/cv&gt;
    &lt;email&gt;
        &lt;from&gt;noreply@idibu.com&lt;/from&gt;
    &lt;/email&gt;
&lt;/data&gt;
XML;

    curl_setopt_array($request = curl_init(), array(
        CURLOPT_URL =&gt; &quot;http://ws.idibu.com/ws/rest/v1/applicants/add-cv?hash=$HASH&quot;,
        CURLOPT_RETURNTRANSFER =&gt; true,
        CURLOPT_POSTFIELDS =&gt; array(
            &#39;data&#39; =&gt; $xml
        )
    ));

    echo curl_exec($request);
    exit();
}
?&gt;
&lt;!DOCTYPE html&gt;
&lt;html&gt;
    &lt;form method=&quot;POST&quot; enctype=&quot;multipart/form-data&quot;&gt;
        &lt;label&gt;CV&lt;/label&gt;
        &lt;input type=&quot;file&quot; name=&quot;cv&quot;&gt;
        &lt;button type=&quot;submit&quot;&gt;Send&lt;/button&gt;
    &lt;/form&gt;
&lt;/html&gt;
</code>
</pre>
