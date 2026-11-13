# bug-hunt-utils entry

`bugs.json` = the entry: `[{fn, input, expected}]` per the challenge README.

Bugs found (all verified locally with `node` against utils.js):
- `factorial(n)`: loop is `i<n`, so it computes (n-1)! — factorial(5) returns 24, not 120.
- `countVowels(s)`: regex `[aeiou]` misses uppercase vowels — "AEIOU" returns 0, not 5.
- `titleCase(s)`: `\b\w` uppercases letters after apostrophes — "don't" becomes "Don'T".
- `average([])`: returns NaN (0/0); canonical reference returns 0.
