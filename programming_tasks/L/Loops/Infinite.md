[1]: http://rosettacode.org/wiki/Loops/Infinite

# [Loops/Infinite][1]

```perl6
loop {
    say 'SPAM';
}
```


In addition, there are various ways of writing lazy, infinite lists in Perl&#160;6:

```perl6
print "SPAM\n" xx *;      # repetition operator
print "SPAM\n", ~* ... *; # sequence operator
map {say "SPAM"}, ^Inf;   # upto operator
```