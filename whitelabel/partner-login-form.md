<p>If you are setting up a whitelabel version of idibu and want to place the login form within your own website or system, the following is an example of the minimum code required to do this:</p>
<pre>
<code>
<form id="idibu_login" action="" method="post">
    <p>
        <label for="idibu_username">Username</label><br />
        <input type="text" id="idibu_username">
    </p>
    <p>
        <label for="idibu_password">Password</label><br />
        <input type="password" id="idibu_password">
    </p>
    <p>
        <button id="idibu_submit">Login</button>
    </p>
</form>
<script type="text/javascript" src="http://www.idibu.com/clients/libs/js/idibu-whitelabel.js"></script>
</code></pre>
