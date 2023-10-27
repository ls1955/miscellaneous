`b` in regexp

Handy when trying to match chars that might be wrap inside non-word chars

```ruby
string = "!tuna! ~ham~ 'yam'=bam="

string.scan /\b[\w]+\b/ # => ["tuna", "ham", "yam", "bam"]
```
