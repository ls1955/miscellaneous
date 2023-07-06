This problem occured at Author's Window 10 device, and not on
Xubuntu device (author have full permission on both devices).

Here is a sample code that recreate the problem.

```ruby
File.new "foo.rb", "w"
File.rename "foo.rb", "new_foo.rb"
=> Errno::EACCES
```

At first glance it seems like a permission error, though further
investigating, it seems like the problem is due to `foo.rb` not
being close beforehand.

As such, the author had resolved the problem by closing the file
beforehand.

```ruby
# 1. Close explicitly
file = File.new "foo.rb", "w"
file.close
File.rename "foo.rb", "new_foo.rb"

# 2. Close by giving a block
File.new("foo.rb", "w") {}
File.rename "foo.rb", "new_foo.rb"
```
