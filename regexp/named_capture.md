```ruby
# Named capture (in Ruby)

# suppose we want to capture a group call <digits>
matches = "abcTuna123".match /(?<digits>\d+)/
matches[:digits] => "123"

# To capture and assign to local variable in Ruby,
# Put regexp on LHS and use =~ operator.
# Docs: https://ruby-doc.org/core-1.9.3/Regexp.html#class-Regexp-label-Capturing
/(?<digits>\d+)/ =~ "1000"
digits # => "1000"

# Note that for above operation, LHS MUST be regexp
# As such, this will not work
re = /(?<digits>\d+)/
re =~ "1000"
digits # => nil
```

