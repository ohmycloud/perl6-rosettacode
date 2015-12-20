[1]: http://rosettacode.org/wiki/Loops/Do-while

# [Loops/Do-while][1]

```perl6
my $val = 0;
repeat {
    say ++$val;
} while $val % 6;
```


`repeat ... until _condition_` is equivalent to `do ... while not _condition_`.

```perl6
my $val = 0;
repeat {
    say ++$val;
} until $val %% 6;
```


(Here we've used `%%`, the "divisible-by" operator.)

```perl6
my $val = 0;
repeat while $val % 6 {
    say ++$val;
}
```