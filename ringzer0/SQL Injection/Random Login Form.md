If you use register form and then login form with the registered values, it will say:
<pre>
Welcome back username, Seems like your not an admin!
</pre>
There's a hint! You need to register as admin. But if you just type 'admin' in username input it will say than user exists.<br>
Hoping that there is syntaxis like
<pre>
... WHERE username LIKE '%username%'
</pre>
Enter a couple of whitespaces to '  admin '.<br>
GL