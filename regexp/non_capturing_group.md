# Non capturing group
```ruby
# Match and not capture sub-pattern
# Taken from mdn web docs: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Regular_expressions/Non-capturing_group
# Suppose we want to match styles.css or styles.[a hex hash].css

def check(path)
  path.match? /styles(?:\.[\da-f]+)?\.css/
end

check "styles.css" # => true
check "styles.a12.css" # => true
check "styles.tuna.ham.css" # => false
```
