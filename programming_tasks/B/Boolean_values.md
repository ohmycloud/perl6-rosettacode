[1]: http://rosettacode.org/wiki/Boolean_values

# [Boolean values][1]

Perl 6 provides an enumeration `Bool` with two values, `True` and `False`. Values of enumerations can be used as ordinary values or as mixins:

```perl
my Bool $crashed = False;
my $val = 0 but True;
```


For a discussion of Boolean context (i.e. how Perl decides whether something is true or false), see [Synopsis 2](http://perlcabal.org/syn/S02.html#Context).