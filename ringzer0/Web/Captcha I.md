Go to http://captcha.ringzer0team.com:7421/form1.php and look at the script in page source:
<pre>
function doIt(){
    var A = document.getElementById('captcha-form').value; 
    if (A == "udifia"){
        document.forms["Form1"].submit();
    }
    else {
        alert("BAD Captcha");
    }
}

</pre>
As you see, validation written on JS. So you can get the captcha value from page.<br>
Write a script which would get this value and submit it. You need to do it 1000 times to get a flag.<br>
GL