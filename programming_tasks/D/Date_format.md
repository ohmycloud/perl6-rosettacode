[1]: http://rosettacode.org/wiki/Date_format

# [Date format][1]

```perl6
use DateTime::Utils;
 
my $dt = DateTime.now;
 
say strftime('%Y-%m-%d', $dt);
say strftime('%A, %B %d, %Y', $dt);
```