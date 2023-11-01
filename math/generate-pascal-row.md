```Crystal
# Suppose we want to generate one of the row in pascal triangle
#
# n
# 1     1
# 2    1 1
# 3   1 2 1
# 4  1 3 3 1

We could do it via certain formula

def pascal_row(n)
  row = [1]

  (1...n).each do |num|
    row << row[-1] * (num - n) // n
  end

  row
end
```
