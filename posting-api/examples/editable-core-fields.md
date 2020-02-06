<p>Some of the core fields (namely, title, reference and description) are &quot;editables&quot;. By adding a parameter named edit with a value of &quot;Yes&quot; will make all the fields marked as editable in the request appear with the sent values in editable text boxes or textareas in the PCP:</p>
<pre>
<code>
&lt;!-- ... --&gt;
&nbsp;&nbsp;&lt;sender id=&quot;31000383&quot;&gt;&lt;/sender&gt;
&nbsp;&nbsp;&lt;title edit=&quot;Yes&quot;&gt;&lt;![CDATA[Here goes the job title]]&gt;&lt;/title&gt;
&nbsp;&nbsp;&lt;description&gt;&lt;![CDATA[This is a job description can be long]]&gt;&lt;/description&gt;
&nbsp;&nbsp;&lt;reference edit=&quot;Yes&quot;&gt;2080&lt;/reference&gt;
&nbsp;&nbsp;&lt;startdate&gt;2011-07-07&lt;/startdate&gt;
&lt;!-- ... --&gt;
</code></pre>
<p>In this case, both the job title and reference are editables, and they will appear in the PCP. Again, by making one of these fields editable it will force the system to return a PCP with every posting.</p>
