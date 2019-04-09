# md5play

## Description 
 Just understand the code ;)

 --------------------------------------------
 Challenge's URL : 
 http://blackfoxs.org/radar/md5play

 Hitting the the url provided we are greated with a php highlited file:
 
 ```php
<?php
if(!isset($_GET['md5'])){die(highlight_file(__FILE__));}
if (isset($_GET['md5']) and strlen($_GET['md5']) == 3 and !is_numeric($_GET['md5'])){
    $md5=$_GET['md5'];
    if (floatval($md5)==md5($md5)){
        die(highlight_file("flag.php"));
    }else{
        echo htmlspecialchars($md5)."!=",md5($md5);
    }
}else{die(highlight_file(__FILE__));}
?> 1
```

 So we need to provide a GET call with the parameter of md5 and the value needs to equal 3 chars and when md5'd needs to equal the float value of the passed value. This will then highlight the flag.php file, if we fail to get flag.php we are given the md5 sum of the value passed.
 We  could bruteforce this with requests and regex for radar{ but before going down that route I tested a couple of values by hand, as luck would have it - third time lucky --:

 http://blackfoxs.org/radar/md5play/?md5=xa.

 Resulting in :

```php
<?php
$flag='radar{s0m3_bug5_1s_fun}';
?> 1
```
