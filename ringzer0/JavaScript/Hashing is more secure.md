As in the first task (and in the all JS tasks) you need to look at script after the .challenge-wrapper:<br>
<pre>

// Look's like weak JavaScript auth script :)
$(".c_submit").click(function(event) {
    event.preventDefault();
    var p = $("#cpass").val();
    if(Sha1.hash(p) == "b89356ff6151527e89c4f3e3d30c8e6586c63962") {
        if(document.location.href.indexOf("?p=") == -1) {   
            document.location = document.location.href + "?p=" + p;
        }
    } else {
        $("#cresponse").html("<div class='alert alert-danger'>Wrong password sorry.</div>");
    }
});
</pre>
So you have sha-1 hash of password. Use any hash decrypt service to know the real pwd. I used http://md5decrypt.net/en/Sha1.<br>
GL