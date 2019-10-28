# coslov: Configfile and Output Stream Line Oriented Verification

This page has just been started

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
