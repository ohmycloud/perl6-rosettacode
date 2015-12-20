[1]: http://rosettacode.org/wiki/Factors_of_an_integer

# [Factors of an integer][1]

```perl6
sub factors (Int $n) { squish sort ($_, $n div $_ if $n %% $_ for 1 .. sqrt $n) }
```