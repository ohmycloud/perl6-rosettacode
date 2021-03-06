[1]: http://rosettacode.org/wiki/Solve_the_no_connection_puzzle

# [Solve the no connection puzzle][1]

Using the Warnsdorff algorithm from [Solve_a_Hidato_puzzle](http://rosettacode.org/wiki/Solve_a_Hidato_puzzle). The idiosyncratic adjacency diagram is dealt with by the simple expedient of bending the two vertical lines `||` into two bows `)(`, such that adjacency can be calculated simply as a distance of 2 or less.

```perl
my @adjacent = gather -> $y, $x {
    take [$y,$x] if abs($x|$y) > 2;
} for -5 .. 5 X -5 .. 5;
 
solveboard q:to/END/;
    . 0 . . 0 .
    . . . . . .
    0 . 0 1 . 0
    . . . . . .
    . 0 . . 0 .
    END
```

#### Output:
```
  4     3  
           
2   8 1   7
           
  6     5  
44 tries
```