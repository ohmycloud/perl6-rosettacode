[1]: http://rosettacode.org/wiki/Call_a_function_in_a_shared_library

# [Call a function in a shared library][1]

```perl
use NativeCall;
 
constant libX11 = '/usr/lib/x86_64-linux-gnu/libX11.so.6';
 
sub XOpenDisplay(Str $s --> Int) is native(libX11) {*}
sub XCloseDisplay(Int $i --> Int) is native(libX11) {*}
 
if try my $d = XOpenDisplay ":0.0" {
    say "ID = $d";
    XCloseDisplay($d);
}
else {
    say "No library {libX11}!";
    say "Use this window instead --> ⬜";
}
```

#### Output:
```
ID = 124842864
```