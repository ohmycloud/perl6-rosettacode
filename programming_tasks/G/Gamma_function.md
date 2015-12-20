[1]: http://rosettacode.org/wiki/Gamma_function

# [Gamma function][1]

```perl6
sub Γ(\z) {
    constant g = 9;
    z < .5 ?? pi/ sin(pi * z) / Γ(1 - z) !!
    sqrt(2*pi) *
    (z + g - 1/2)**(z - 1/2) *
    exp(-(z + g - 1/2)) *
    [+] <
        1.000000000000000174663
     5716.400188274341379136
   -14815.30426768413909044
    14291.49277657478554025
    -6348.160217641458813289
     1301.608286058321874105
     -108.1767053514369634679
        2.605696505611755827729
       -0.7423452510201416151527e-2
        0.5384136432509564062961e-7
       -0.4023533141268236372067e-8
    > Z* 1, |map 1/(z + *), 0..*
}
 
say Γ($_) for 1/3, 2/3 ... 10/3;
```

#### Output:
```
2.67893853470775
1.3541179394264
1
0.892979511569248
0.902745292950934
1
1.190639348759
1.50457548825155
2
2.77815848043766
```