[1]: http://rosettacode.org/wiki/Assertions

# [Assertions][1]

*Note: This example does not work in the primary Perl 6 compiler, Rakudo.*

```perl
my $a = (1..100).pick;
 
# with a (non-hygienic) macro
macro assert ($x) { "$x or die 'assertion failed: $x'" }
assert('$a == 42');
 
# but usually we just say
$a == 42 or die '$a ain\'t 42';
```