[1]: http://rosettacode.org/wiki/Non-decimal_radices/Convert

# [Non-decimal radices/Convert][1]

```perl6
sub from-base(Str $str, Int $base) {
    +":$base\<$str>";
}
 
sub to-base(Real $num, Int $base) {
    $num.base($base);
}
```


These work on any real type including integer types.