[1]: http://rosettacode.org/wiki/LZW_compression

# [LZW compression][1]

```perl6
sub compress(Str $uncompressed --> Seq)  { 
    my $dict-size = 256;
    my %dictionary = (.chr => .chr for ^$dict-size);
 
    my $w = "";
    gather {
	for $uncompressed.comb -> $c {
	    my $wc = $w ~ $c;
	    if %dictionary{$wc}:exists { $w = $wc }
	    else {
		take %dictionary{$w};
		%dictionary{$wc} = +%dictionary;
		$w = $c;
	    }
	}
 
	take %dictionary{$w} if $w.chars;
    }
}
 
sub decompress(@compressed --> Str) { 
    my $dict-size = 256;
    my %dictionary = (.chr => .chr for ^$dict-size);
 
    my $w = shift @compressed;
    join '', gather {
	take $w;
	for @compressed -> $k {
	    my $entry;
	    if %dictionary{$k}:exists { take $entry = %dictionary{$k} }
	    elsif $k == $dict-size    { take $entry = $w ~ $w.substr(0,1) }
	    else                      { die "Bad compressed k: $k" }
 
	    %dictionary{$dict-size++} = $w ~ $entry.substr(0,1);
	    $w = $entry;
	}
    }
}
 
my @compressed = compress('TOBEORNOTTOBEORTOBEORNOT');
say @compressed;
my $decompressed = decompress(@compressed);
say $decompressed;
```

#### Output:
```
T O B E O R N O T 256 258 260 265 259 261 263
TOBEORNOTTOBEORTOBEORNOT
```