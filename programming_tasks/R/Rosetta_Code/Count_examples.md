[1]: http://rosettacode.org/wiki/Rosetta_Code/Count_examples

# [Rosetta Code/Count examples][1]

```perl
use LWP::Simple;
 
my $site = "http://rosettacode.org";
my $list-url = "/mw/api.php?action=query&list=categorymembers&cmtitle=Category:Programming_Tasks&cmlimit=500&format=xml";
 
for get("$site$list_url").comb(/'cm' .*? 'title="' <( .*? )> '"'/) {
    my $slug = .trans(' ' => '_');
    my $count = +get("$site/wiki/$slug").comb(/'toclevel-1'/);
    say "$_: $count examples";
}
```