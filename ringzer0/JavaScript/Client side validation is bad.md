You need to check the source code of html page.<br>
Search for auth script after the .challenge-wrapper:
<pre>

// Look's like weak JavaScript auth script :)
$(".c_submit").click(function(event) {
    event.preventDefault()
    var u = $("#cuser").val();
    var p = $("#cpass").val();
    if(u == "admin" && p == String.fromCharCode(74,97,118,97,83,99,114,105,112,116,73,115,83,101,99,117,114,101)) {
        if(document.location.href.indexOf("?p=") == -1) {   
            document.location = document.location.href + "?p=" + p;
        }
    } else {
        $("#cresponse").html("<div class='alert alert-danger'>Wrong password sorry.</div>");
    }
});	
</pre>
Login equals 'admin'. <br>
To know password you need to execute 'String.fromCharCode(74,97,118,97,83,99,114,105,112,116,73,115,83,101,99,117,114,101)' in console.<br>
After this you will get a password - 'JavaScriptIsSecure'.<br>
Then just go to https://ringzer0team.com/challenges/27/?p=JavaScriptIsSecure or insert login and password and submit form.<br>
GL.
