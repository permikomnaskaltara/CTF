Source code of task:
<pre>
<?
if(isset($_POST['reset_username'])) {
		srand(time());
		$token =
		rand(1000000000000000,9999999999999999);
				
		$success = '<div class="success">Reset password link has been sent to admin@youdontownthisemail.com. Please follow the link ...';
		$hSql->FastQuery('DELETE FROM chal_113 WHERE ip_addr = ?', array($_SERVER['REMOTE_ADDR']));
		$hSql->FastQuery('insert into chal_113 values (?,?,?)', array($_SERVER['REMOTE_ADDR'], $token, time() + 3600));
}

if(URL_HANDLE::GetInstance()->get->k != null) {
		$result = reset($hSql->FastQuery('SELECT * FROM chal_113 WHERE ip_addr = ? AND recovery_key = ? ', array($_SERVER['REMOTE_ADDR'], URL_HANDLE::GetInstance()->get->k)));
		if($hSql->RowCount() != 0) {
				if($result->expired_time > time()) {
						$success = '<div class="success">Here\'s your new password: XXXXXXXXXXXXXX</div>';
				} else {
						$success = '<div class="error">Expired recovery key!</div>';
				}
		} else {
				$success = '<div class="error">Invalid recovery key!</div>';
		}
}
</pre>
So you need to generate token, sent to email.<br>
Function srand depends on current time (unix timestamp).<br>
Current time diplayed in the bottom of the form.<br>
Just convert it to a unix timestamp here http://www.unixtimestamp.com/ and save the value.
<pre>
srand(your_timestamp_value);
$token = rand(1000000000000000,9999999999999999);
echo $tocken;
</pre>
Then go to a http://ringzer0team.com/challenges/113/?k= + your tocken.<br>
GL