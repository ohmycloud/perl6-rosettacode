[1]: http://rosettacode.org/wiki/Longest_Common_Substring

# [Longest Common Substring][1]

```perl
use v6;
 
sub createSubstrings( Str $word --> Array ) {
   my $length = $word.chars ;
   my @substrings ;
   for (0..$length - 1) -> $start {
      for (1..$length - $start) -> $howmany {
	 @substrings.push( $word.substr( $start , $howmany ) ) ;
      }
   }
   return @substrings ;
}
 
sub findLongestCommon( Str $first , Str $second --> Str ) {
   my @substringsFirst = createSubstrings( $first ) ;
   my @substringsSecond = createSubstrings( $second ) ;
   my $firstset = set( @substringsFirst ) ;
   my $secondset = set( @substringsSecond ) ;
   my $common = $firstset (&) $secondset ;
   return $common.keys.sort({$^b.chars <=> $^a.chars})[0] ;
}
 
sub MAIN( Str $first , Str $second ) {
   my $phrase = "The longest common substring of $first and $second is " ~
   "{findLongestCommon( $first , $second ) } !" ;
   $phrase.say ;
}
```

#### Output:
```
The longest common substring of thisisatest and testing123testing is test !
```