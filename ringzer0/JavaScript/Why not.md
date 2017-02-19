This time we have a cryptography script which protects password.
<pre>

// Look's like weak JavaScript auth script :)
$(".c_submit").click(function(event) {
    event.preventDefault();
    var k = new Array(176,214,205,246,264,255,227,237,242,244,265,270,283);
    var u = $("#cuser").val();
    var p = $("#cpass").val();
    var t = true;

    if(u == "administrator") {
        for(i = 0; i < u.length; i++) {
            if((u.charCodeAt(i) + p.charCodeAt(i) + i * 10) != k[i]) {
                $("#cresponse").html("<div class='alert alert-danger'>Wrong password sorry.</div>");
                t = false;
                break;
            }
        }
    } else {
        $("#cresponse").html("<div class='alert alert-danger'>Wrong password sorry.</div>");
        t = false;
    }
    if(t) {
        if(document.location.href.indexOf("?p=") == -1) {
            document.location = document.location.href + "?p=" + p;
            }
    }
});	
</pre>
So the password calculation is u.charCodeAt(i) + p.charCodeAt(i) + i * 10). Login = 'administrator'.<br>
Use console and get a password:
<pre>
var k = new Array(176,214,205,246,264,255,227,237,242,244,265,270,283);
var pwd = [];
var u = 'administrator';
for(i = 0; i < u.length; i++) {
    pwd.push(k[i] - i*10 - u.charCodeAt(i));
  } 
String.fromCharCode.apply(null, pwd);
</pre>
Output is: OhLord4309111.<br>
GL