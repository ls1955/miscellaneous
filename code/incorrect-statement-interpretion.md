Suppose we have this statement in Crystal:

```Crystal
# {a, b}, {c, d} : Tuple(Int32, Int32)
{a, b} < {c, d}
```

Might think that above statement is equal to this:
```Crystal
a < c && b < d
```

...not exactly correct, due to how comparison work in Crystal (and Ruby).

Below is the correct statement (in this case):
```Crystal
a <= c && b < d
# if a <= c, check next element
```

# Fun fact:
This incorrect comprehension of statement had caused author 2 days in [Advent of Code year 2018 day 15](https://adventofcode.com/2018/day/15). :)