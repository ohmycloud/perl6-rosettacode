[1]: http://rosettacode.org/wiki/Multiplication_tables

# [Multiplication tables][1]

```perl
my $max = 12;
my $width = chars $max**2;
my $f = "%{$width}s";
 
say 'x'.fmt($f), '┃ ', (1..$max).fmt($f);
say '━' x $width, '╋', '━' x $max*$width + $max;
for 1..$max -> $i {
    say $i.fmt($f), '┃ ', (
        for 1..$max -> $j {
            $i <= $j ?? $i*$j !! '';
        }
    ).fmt($f);
}
```


<code>


#### Output:
```
  x┃   1   2   3   4   5   6   7   8   9  10  11  12
━━━╋━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  1┃   1   2   3   4   5   6   7   8   9  10  11  12
  2┃       4   6   8  10  12  14  16  18  20  22  24
  3┃           9  12  15  18  21  24  27  30  33  36
  4┃              16  20  24  28  32  36  40  44  48
  5┃                  25  30  35  40  45  50  55  60
  6┃                      36  42  48  54  60  66  72
  7┃                          49  56  63  70  77  84
  8┃                              64  72  80  88  96
  9┃                                  81  90  99 108
 10┃                                     100 110 120
 11┃                                         121 132
 12┃                                             144
```


</code>