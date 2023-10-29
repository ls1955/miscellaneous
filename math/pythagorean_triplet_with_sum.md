# Question
```
Given a number 'n', find all pythagorean triplet (a, b, c) such that:

1. a + b + c == n
2. a**2 + b**2 == c**2
3. a < b < c
```

# Solution
```
1. Fixed the value of a from 2 upto (n / 2)
2. For each a:
     let b = (n * (n / 2 - a)) / (n - a)
     let c = Integer.sqrt(a**2 + b**2)

     valid_triplet if a < b < c && a**2 + b**2 == c**2
```

## Ruby implementation
```Ruby
def self.triplets_with_sum(n)
  result = []

  (2..(n / 2)).each do |a|
    b = (n * (n / 2 - a)) / (n - a)
    c = Integer.sqrt(a**2 + b**2)

    result << [a, b, c] if a < b && b < c && a**2 + b**2 == c**2
  end

  result
end
```

## Note
```
Author have no idea how that formula is being derived, why does it work, etc...
He will be very grateful if someone could shed some pearl of wisdom on this topic.
```
