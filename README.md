# coslov: Configfile and Output Stream Line Oriented Verification

This page has just been started, and currently only documents some ideas without an actual implementation.

## Syntax
```
@def int: [1-9][0-9[*
@def date: [1-9][0-9][0-9][0-9]-[0-1][0-9]-[0-3][0-9]

Some line that contains date @<date>
Some line that contains regep @<'${[^}]*}'>
Special characters & and  > in regexep @<'&amp; and &gt;'>

@optional: line may be missing

@begin unordered
  @begin repeat
  indenting is optional, will be removed
  @end
@end
```

## Repeat options
```
@repeat=1-5: 1 to 5 items
@repeat=0-...: zero to any times
@repeat=*: synonym for repeat=0-...
@repeat=+: synonym for repeat=1-...
@repeat=?: synonym for repeat=0-1
@optional: synonym for repeat=0-1
```

## Order options
```
@begin order=strict: (default), the following items must occur in this order
  line1
  line2
  line3
@end

@begin order=random: the following items may occur in any order
  some-line
  another-line
@end

@begin order=only-one: only one item may occur
  option1
  option2
  option3
@end
```

## Example
```
@begin optional
#######@<#*>
# SECTION: dns
  dns_ip: @<ipv4>
  @begin optional:dns_entries:
  @repeat *      :- @<fqdn> @<ipv4>
  @end
@end
```
