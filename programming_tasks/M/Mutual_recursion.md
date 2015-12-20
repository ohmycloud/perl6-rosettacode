[1]: http://rosettacode.org/wiki/Mutual_recursion

# [Mutual recursion][1]

A direct translation of the definitions of <span class="texhtml" dir="ltr">_F_</span> and <span class="texhtml" dir="ltr">_M_</span>:

```perl6
multi F(0) { 1 }; multi M(0) { 0 }
multi F(\𝑛) { 𝑛 - M(F(𝑛 - 1)) }
multi M(\𝑛) { 𝑛 - F(M(𝑛 - 1)) }
 
say map &F, ^20;
say map &M, ^20;
```

#### Output:
```
1 1 2 2 3 3 4 5 5 6 6 7 8 8 9 9 10 11 11 12
0 0 1 2 2 3 4 4 5 6 6 7 7 8 9 9 10 11 11 12
```